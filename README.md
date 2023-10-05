# Multilingual-Speech-Commands-Dataset

## Dataset
Multilingual Speech Commands (MSC) dataset represents utterances for 35 keywords in Kazakh, Tatar, and Russian. In total, the dataset contains 3,623 utterances (119 speakers) in Kazakh, 3,547 utterances (153 speakers) in Tatar, and 1,625 utterances (54 speakers) in Russian. Overall, the dataset provides ~100 utterances per command for the Kazakh and Tatar languages and ~50 utterances per command for the Russian language. The utterances are one-second duration and saved in WAV format with a sampling rate of 16 kHz. The dataset can be downloaded from [Google Drive](https://drive.google.com/file/d/1yXkriMPwc1PVt2lyvwrJx_x91f-aqVBy/view?usp=sharing). 

|ID|English|Kazakh|Tatar|Russian|
|--|--------|--------|--------|--------|
|1|backward|артқа|артка|назад|
|2|forward|алға|алга|вперед|
|3|right|оңға|уңга|направо|
|4|left|солға|сулга|налево|
|5|down|төмен|аска|вниз|
|6|up|жоғары|өскә|вверх|
|7|go|жүр|бар|иди|
|8|stop|тоқта|тукта|стой|
|9|on|қос|кабыз|включи|
|10|off|өшір|сүндер|выключи|
|11|yes|иә|әйе|да|
|12|no|жоқ|юк|нет|
|13|learn|үйрен|өйрән|учись|
|14|follow|орында|ияреп бар|следуй|
|15|zero|нөл|ноль|ноль|
|16|one|бір|бер|один|
|17|two|екі|ике|два|
|18|three|үш|өч|три|
|19|four|төрт|дүрт|четыре|
|20|five|бес|биш|пять|
|21|six|алты|алты|шесть|
|22|seven|жеті|җиде|семь|
|23|eight|сегіз|сигез|восемь|
|24|nine|тоғыз|тугыз|девять|
|25|bed|төсек|карават|кровать|
|26|bird|құс|кош|птица|
|27|cat|мысық|мәче|кошка|
|28|dog|ит|эт|собака|
|29|happy|бақытты|бәхетле|счастливый|
|30|house|үй|өй|дом|
|31|read|оқы|укы|читай|
|32|write|жаз|яз|пиши|
|33|tree|ағаш|агач|дерево|
|34|visual|көрнекі|визуаль|визуальный|
|35|wow|мәссаған|о|ух ты|

## Checkpoints
Pretrained models can be downloaded from Google Drive. The following table provides links for downloading the models and accuracy (%) of each model on the test sets. 
|Model|Checkpoint|Acc (kk)|Acc (tt)|Acc (ru)|Acc (en)|
|------|--------|--------|--------|--------|--------|
|Mono-35-kk|[Google Drive](https://drive.google.com/drive/folders/181Tij98H6VhQQiFevM6dvy7U_Kc-HUfv?usp=sharing)|97.43|-|-|-|
|Mono-35-tt|[Google Drive](https://drive.google.com/drive/folders/1o56cNRDNwbLnx3R8MCUlMZsLgsOWmf2M?usp=sharing)|-|98.67|-|-|
|Mono-35-ru|[Google Drive](https://drive.google.com/drive/folders/1UKeiXePF48h9MY6QNF6aP6dSOC3riSdS?usp=sharing)|-|-|95.43|-|
|Mono-35-en|[Google Drive](https://drive.google.com/drive/folders/1u43MmbHOqvqoI12O8pd3JHpo0tovkELQ?usp=sharing)|-|-|-|97.24|
|Multi-35|[Google Drive](https://drive.google.com/drive/folders/1-ImbRPCijLg0wdvo6-jd47vIs3kPY_rH?usp=sharing)|**98.57**|**99.33**|**96.86**|**97.33**|
|Multi-140|[Google Drive](https://drive.google.com/drive/folders/12p5lrdqOs-cOtyW5BolFMyh2vVsBfy1w?usp=sharing)|97.71|99.24|96.57|97.12|
