# project3
import random
def add_noise(power_consumption):
    # افزودن نویز به طور تصادفی
    noise = random.uniform(-0.1, 0.1) 
    noisy_power = power_consumption + noise
    return noisy_power

# شبیه‌سازی محاسبه مصرف توان با و بدون نویز
def simulate_power_consumption(num_trials):
    success_count = 0
    base_power_consumption = 10.0  # مصرف توان بدون نویز

    for _ in range(num_trials):
        noisy_power_consumption = add_noise(base_power_consumption)

        # اینجا می‌توانید یک شرط تعیین کنید که در صورت تحقق آن به عنوان موفقیت در نظر بگیریم.
        # به طور مثال، می‌توانیم بگوییم اگر مصرف توان بیشتر از 10.05 یا کمتر از 9.95 باشد، آن را به عنوان حمله تشخیص دهیم.
        if noisy_power_consumption > 10.05 or noisy_power_consumption < 9.95:
            success_count += 1
    
    success_rate = success_count / num_trials * 100
    print(f"     succes rate of countermeasure against power attack: {success_rate}%")

simulate_power_consumption(1000)
