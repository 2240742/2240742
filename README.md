- 👋 Hi, I’m @2240742
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
2240742/2240742 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
import java.util.Scanner;

public class ZodiacSignFinder {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // ユーザーから月と日を入力
        System.out.print("生まれた月を入力してください（1～12）: ");
        int month = scanner.nextInt();

        System.out.print("生まれた日を入力してください（1～31）: ");
        int day = scanner.nextInt();

        // 入力の妥当性をチェック
        if (!isValidDate(month, day)) {
            System.out.println("無効な日付です。正しい月と日を入力してください。");
            scanner.close();
            return;
        }

        // 星座を判定
        String zodiac = getZodiacSign(month, day);

        // 結果を出力
        System.out.println("あなたの星座は: " + zodiac + " です。");

        scanner.close();
    }

    // 日付の妥当性を確認するメソッド
    public static boolean isValidDate(int month, int day) {
        if (month < 1 || month > 12) {
            return false;
        }

        // 各月の日数
        int[] daysInMonth = {
            31, // 1月
            29, // 2月（閏年を考慮して29日とする）
            31, // 3月
            30, // 4月
            31, // 5月
            30, // 6月
            31, // 7月
            31, // 8月
            30, // 9月
            31, // 10月
            30, // 11月
            31  // 12月
        };

        if (day < 1 || day > daysInMonth[month - 1]) {
            return false;
        }

        return true;
    }

    // 星座を判定するメソッド
    public static String getZodiacSign(int month, int day) {
        switch (month) {
            case 1:
                return (day <= 19) ? "山羊座" : "水瓶座";
            case 2:
                return (day <= 18) ? "水瓶座" : "魚座";
            case 3:
                return (day <= 20) ? "魚座" : "牡羊座";
            case 4:
                return (day <= 19) ? "牡羊座" : "牡牛座";
            case 5:
                return (day <= 20) ? "牡牛座" : "双子座";
            case 6:
                return (day <= 20) ? "双子座" : "蟹座";
            case 7:
                return (day <= 22) ? "蟹座" : "獅子座";
            case 8:
                return (day <= 22) ? "獅子座" : "乙女座";
            case 9:
                return (day <= 22) ? "乙女座" : "天秤座";
            case 10:
                return (day <= 22) ? "天秤座" : "蠍座";
            case 11:
                return (day <= 21) ? "蠍座" : "射手座";
            case 12:
                return (day <= 21) ? "射手座" : "山羊座";
            default:
                return "不明な星座";
        }
    }
}

