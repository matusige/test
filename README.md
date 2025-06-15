# test# 1から指定した数までを足すプログラム

def sum_numbers(n):
    """
    1からnまでの数を足す関数
    """
    if n <= 0:
        return 0
    
    total = 0
    for i in range(1, n + 1):
        total += i
    
    return total

def sum_numbers_formula(n):
    """
    数学公式を使った効率的な方法: n(n+1)/2
    """
    if n <= 0:
        return 0
    
    return n * (n + 1) // 2

# メイン処理
if __name__ == "__main__":
    try:
        # ユーザーから数値を入力してもらう
        num = int(input("どこまでの数を足しますか？: "))
        
        if num < 1:
            print("1以上の数を入力してください。")
        else:
            # ループを使った方法
            result1 = sum_numbers(num)
            print(f"ループ使用: 1から{num}まで足すと {result1} です")
            
            # 公式を使った方法
            result2 = sum_numbers_formula(num)
            print(f"公式使用: 1から{num}まで足すと {result2} です")
            
            # 計算過程を表示（数が小さい場合のみ）
            if num <= 20:
                numbers = " + ".join(str(i) for i in range(1, num + 1))
                print(f"計算過程: {numbers} = {result1}")
    
    except ValueError:
        print("正しい数値を入力してください。")