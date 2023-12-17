################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include MCAL/TIMER/subdir.mk
-include MCAL/PWM/subdir.mk
-include MCAL/INTERRUPT/subdir.mk
-include MCAL/subdir.mk
-include HAL/USS/subdir.mk
-include HAL/SERVO/subdir.mk
-include HAL/MOTOR/subdir.mk
-include HAL/CLCD/subdir.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(ASM_DEPS)),)
-include $(ASM_DEPS)
endif
ifneq ($(strip $(S_DEPS)),)
-include $(S_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
endif

-include ../makefile.defs

# Add inputs and outputs from these tool invocations to the build variables 
LSS += \
autonomous-car-project.lss \

FLASH_IMAGE += \
autonomous-car-project.hex \

SIZEDUMMY += \
sizedummy \


# All Target
all: autonomous-car-project.elf secondary-outputs

# Tool invocations
autonomous-car-project.elf: $(OBJS) $(USER_OBJS)
	@echo 'Building target: $@'
	@echo 'Invoking: AVR C Linker'
	avr-gcc -Wl,-Map,autonomous-car-project.map -mmcu=atmega32 -o "autonomous-car-project.elf" $(OBJS) $(USER_OBJS) $(LIBS)
	@echo 'Finished building target: $@'
	@echo ' '

autonomous-car-project.lss: autonomous-car-project.elf
	@echo 'Invoking: AVR Create Extended Listing'
	-avr-objdump -h -S autonomous-car-project.elf  >"autonomous-car-project.lss"
	@echo 'Finished building: $@'
	@echo ' '

autonomous-car-project.hex: autonomous-car-project.elf
	@echo 'Create Flash image (ihex format)'
	-avr-objcopy -R .eeprom -R .fuse -R .lock -R .signature -O ihex autonomous-car-project.elf  "autonomous-car-project.hex"
	@echo 'Finished building: $@'
	@echo ' '

sizedummy: autonomous-car-project.elf
	@echo 'Invoking: Print Size'
	-avr-size --format=avr --mcu=atmega32 autonomous-car-project.elf
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) $(FLASH_IMAGE)$(ELFS)$(OBJS)$(ASM_DEPS)$(S_DEPS)$(SIZEDUMMY)$(S_UPPER_DEPS)$(LSS)$(C_DEPS) autonomous-car-project.elf
	-@echo ' '

secondary-outputs: $(LSS) $(FLASH_IMAGE) $(SIZEDUMMY)

.PHONY: all clean dependents
.SECONDARY:

-include ../makefile.targets
