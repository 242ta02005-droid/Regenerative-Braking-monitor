# Regenerative-Braking-monitor
# Regenerative Braking Monitor
# Simulation Program

print("======================================")
print("       REGENERATIVE BRAKING MONITOR")
print("======================================")

# Safe limits
MAX_BATTERY_VOLTAGE = 420
MAX_CHARGING_CURRENT = 50

# Input values
speed = float(input("Enter motor speed (RPM): "))
brake = input("Is regenerative braking active? (yes/no): ").lower()
battery_voltage = float(input("Enter battery voltage (V): "))
charging_current = float(input("Enter charging current (A): "))

print("\n--- System Status ---")

if battery_voltage > MAX_BATTERY_VOLTAGE:
    print("⚠️ Battery overvoltage detected!")
    print("🔴 Regenerative braking disabled.")

elif charging_current > MAX_CHARGING_CURRENT:
    print("⚠️ Charging current too high!")
    print("🔴 Regenerative braking disabled.")

elif brake == "yes" and speed > 0:
    regenerative_power = battery_voltage * charging_current

    print("🟢 Regenerative braking ACTIVE")
    print("Motor Speed       :", speed, "RPM")
    print("Battery Voltage   :", battery_voltage, "V")
    print("Charging Current  :", charging_current, "A")
    print("Regenerative Power:", round(regenerative_power, 2), "W")
    print("🔋 Energy is being returned to the battery.")

else:
    print("⚪ Regenerative braking INACTIVE")
    print("Motor operating normally.")
