# LV1
def calculate_runtime(load_power, battery_capacity, battery_voltage, efficiency):
    """
    計算 UPS 備援時間

    load_power: 負載功率 (W)
    battery_capacity: 電池容量 (Ah)
    battery_voltage: 電池電壓 (V)
    efficiency: 系統效率 (0~1)
    """

    energy = battery_voltage * battery_capacity
    available_energy = energy * efficiency

    runtime_hours = available_energy / load_power
    runtime_minutes = runtime_hours * 60

    return runtime_minutes


def runtime_category(minutes):
    """備援時間等級判斷"""

    if minutes < 10:
        return "備援時間：短"
    elif minutes < 30:
        return "備援時間：中"
    else:
        return "備援時間：長"


def main():

    print("UPS 電池備援時間計算器")
    print("----------------------")

    try:
        load_power = float(input("請輸入負載功率 (W): "))
        battery_capacity = float(input("請輸入電池容量 (Ah): "))
        battery_voltage = float(input("請輸入電池電壓 (V): "))
        efficiency = float(input("請輸入系統效率 (%) : ")) / 100

        if load_power <= 0 or battery_capacity <= 0 or battery_voltage <= 0:
            print("輸入值必須大於 0")
            return

        runtime = calculate_runtime(
            load_power,
            battery_capacity,
            battery_voltage,
            efficiency
        )

        print("\n預估備援時間：{:.2f} 分鐘".format(runtime))
        print(runtime_category(runtime))

    except ValueError:
        print("輸入格式錯誤，請輸入數字")


if __name__ == "__main__":
    main()
