```
name: learn-github-actions
```
İsteğe bağlı - iş akışının adı
```
on: [push]
```
Bu iş akışı için tetikleyiciyi belirtir. Bu örnek, push olayını kullanır, bu nedenle, biri havuzda bir değişiklik yaptığında veya bir çekme isteğini birleştirdiğinde bir iş akışı çalıştırması tetiklenir.
```
jobs:
```
Learn-github-actions iş akışında çalışan tüm işleri gruplandırır.

```
check-bats-version:
```
Check-bats-version adlı bir işi tanımlar. Alt anahtarlar, işin özelliklerini tanımlayacaktır.

```
  runs-on: ubuntu-latest
  ```
İşi, bir Ubuntu Linux çalıştırıcısının en son sürümünde çalışacak şekilde yapılandırır. Bu, işin GitHub tarafından barındırılan yeni bir sanal makinede yürütüleceği anlamına gelir.

```
  steps:
```
Check-yarasalar-sürüm işinde çalışan tüm adımları birlikte gruplandırır. Bu bölümün altına yerleştirilmiş her öğe, ayrı bir eylem veya kabuk komut dosyasıdır.

    - uses: actions/checkout@v3
Anahtar usessözcük, bu adımın v3eylemi gerçekleştireceğini actions/checkoutbelirtir. Bu, koşucudaki havuzunuzu denetleyen ve kodunuza karşı komut dosyaları veya diğer eylemleri (derleme ve test araçları gibi) çalıştırmanıza izin veren bir eylemdir.

    - uses: actions/setup-node@v3
      with:
        node-version: '14'
Bu adım , Node.js'nin belirtilen sürümünü yüklemek için eylemi kullanır (bu örnekte v14 kullanılır). Bu, hem actions/setup-node@v3 ve  node npm PATH komutlarını kullanır.

    - run: npm install -g bats
run anahtar sözcüğü, işe koşucu üzerinde bir komut yürütmesini söyler. Bu durumda, bats yazılım test paketini kurmak için npm kullanıyorsunuz.

    - run: bats -v
Son olarak, yazılım sürümünü veren bir parametreyle bats komutunu çalıştıracaksınız.
