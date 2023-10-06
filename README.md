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

## Model Training and Testing
We employed the [Keyword-MLP](https://github.com/AI-Research-BD/Keyword-MLP) model in this project. We sincerely thank the authors for open-sourcing the code. 
1. Download the code and install the required packages
```
git clone https://github.com/fair-ai-lab/Multilingual-Speech-Commands-Dataset.git
pip install -r requirements.txt
```
2. Download and unzip the dataset

We augmented the dataset for Kazakh, Russian, and Tatar to increase the dataset size. The augmented dataset can be downloaded from [Google Drive](https://drive.google.com/file/d/1ltZJj95J5zBDp6rmoEomJxJzN4Rb8WAF/view?usp=sharing).
The statistics of the augmented dataset as follows:

|Dataset|Train|Validation|Test|
|------|--------|--------|--------|
|Kazakh | 80,028	| 12,600	| 10,500 |
|Tatar | 77,292	| 12,600	| 10,500 |
|Russian | 58,275	| -	| 7,000 |
|Google Speech Commands v2 | 84,843	| 9,981	| 11,005 |

3. To train Keyword-MLP as a monolingual speech command recognition model, update paths to dataset in each configuration file and run the following commands: 
   
Kazakh language:
```
python train.py --conf configs/kwmlp_kscd.yaml
```
Tatar language:
```
python train.py --conf configs/kwmlp_tscd.yaml
```
Russian language:
```
python train.py --conf configs/kwmlp_rscd.yaml
```
English language:
```
python train.py --conf configs/kwmlp_google.yaml
```

4. To train Keyword-MLP as a multilingual speech command recognition model, update paths to dataset in each configuration file and run the following commands: 
   
Multi-35:
```
python train.py --conf configs/kwmlp_multi_35.yaml
```
Multi-140:
```
python train.py --conf configs/kwmlp_multi_140.yaml
```
5. To evaluate the monolingual and multilingual models, download the test set from [Google Drive](https://drive.google.com/file/d/1EFUIQxD2RxGA5BkkCEsSoEkv6HbswgyD/view?usp=sharing) and run the following notebooks:

```eval_kk.ipynb```, ```eval_ru.ipynb```, ```eval_tt.ipynb```, and ```eval_en.ipynb``` 

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
