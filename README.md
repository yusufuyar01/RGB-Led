# RGB LED Kontrol Projesi

Bu proje, Arduino kullanarak kırmızı, yeşil ve mavi LED'leri kontrol etmeyi ve farklı renk kombinasyonları oluşturmayı amaçlar.

## İçindekiler

- [Açıklama](#açıklama)
- [Gereksinimler](#gereksinimler)
- [Kurulum](#kurulum)
- [Kullanım](#kullanım)
- [Kod Açıklaması](#kod-açıklaması)
- [Görsel](#görsel)

## Açıklama

Bu proje, Arduino platformu kullanılarak RGB LED'lerin nasıl kontrol edileceğini ve farklı renklerin nasıl elde edileceğini gösterir. Projede, kırmızı, yeşil ve mavi LED'ler belirli bir sırayla yanar ve farklı renk kombinasyonları oluşturur.

## Gereksinimler

- Arduino kartı (Örneğin, Arduino Uno)
- 3 adet LED (Kırmızı, Yeşil, Mavi)
- 3 adet direnç (220-330 ohm önerilir)
- Jumper kabloları
- Breadboard (İsteğe bağlı)
- Arduino IDE yazılımı

## Kurulum

1. Arduino IDE yazılımını indirin ve kurun.
2. Arduino kartınızı bilgisayara bağlayın.
3. Arduino IDE'de doğru kartı ve portu seçin.
4. Aşağıdaki kodu Arduino IDE'ye kopyalayın.
5. Kodu Arduino kartınıza yükleyin.
6. LED'leri, dirençleri ve jumper kablolarını breadboard üzerine veya doğrudan Arduino kartına bağlayın. Bağlantıları aşağıdaki gibi yapın:
    - Kırmızı LED'in uzun bacağını (anot) 8. pine, kısa bacağını (katot) bir dirence ve direncin diğer ucunu GND'ye bağlayın.
    - Yeşil LED'in uzun bacağını 9. pine, kısa bacağını bir dirence ve direncin diğer ucunu GND'ye bağlayın.
    - Mavi LED'in uzun bacağını 10. pine, kısa bacağını bir dirence ve direncin diğer ucunu GND'ye bağlayın.

![Image](https://github.com/user-attachments/assets/66e8613d-2d10-481e-933d-ccc73b76d979)

## Kullanım

Proje yüklendikten sonra, LED'ler aşağıdaki sırayla yanacaktır:

1. Tüm LED'ler söner.
2. Kırmızı LED yanar.
3. Yeşil LED yanar.
4. Mavi LED yanar.
5. Sarı renk için kırmızı ve yeşil LED'ler aynı anda yanar.
6. Beyaz renk için tüm LED'ler yanar.

Bu döngü sürekli olarak tekrar eder.

## Kod Açıklaması

```c++
int kirmiziPin = 8; // Kırmızı LED'in bağlı olduğu pin
int yesilPin = 9;  // Yeşil LED'in bağlı olduğu pin
int maviPin = 10; // Mavi LED'in bağlı olduğu pin

void setup() {
  pinMode(kirmiziPin, OUTPUT); // Kırmızı LED pinini çıkış olarak ayarlar
  pinMode(yesilPin, OUTPUT);  // Yeşil LED pinini çıkış olarak ayarlar
  pinMode(maviPin, OUTPUT);  // Mavi LED pinini çıkış olarak ayarlar
}

void loop() {
  // Tüm LED'leri söndür
  digitalWrite(kirmiziPin, LOW);
  digitalWrite(yesilPin, LOW);
  digitalWrite(maviPin, LOW);
  delay(1000); // 1 saniye bekle

  // Kırmızı LED'i yak
  digitalWrite(kirmiziPin, HIGH);
  digitalWrite(yesilPin, LOW);
  digitalWrite(maviPin, LOW);
  delay(1000); // 1 saniye bekle

  // Yeşil LED'i yak
  digitalWrite(kirmiziPin, LOW);
  digitalWrite(yesilPin, HIGH);
  digitalWrite(maviPin, LOW);
  delay(1000); // 1 saniye bekle

  // Mavi LED'i yak
  digitalWrite(kirmiziPin, LOW);
  digitalWrite(yesilPin, LOW);
  digitalWrite(maviPin, HIGH);
  delay(1000); // 1 saniye bekle

  // Sarı renk için kırmızı ve yeşil LED'leri aynı anda yak
  digitalWrite(kirmiziPin, HIGH);
  digitalWrite(yesilPin, HIGH);
  digitalWrite(maviPin, LOW);
  delay(1000); // 1 saniye bekle

  // Beyaz renk için tüm LED'leri yak
  digitalWrite(kirmiziPin, HIGH);
  digitalWrite(yesilPin, HIGH);
  digitalWrite(maviPin, HIGH);
  delay(1000); // 1 saniye bekle
} 
