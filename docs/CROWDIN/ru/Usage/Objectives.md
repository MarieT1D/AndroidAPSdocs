# Цели

AndroidAPS ставит ряд Целей, которые необходимо выполнить, чтобы подготовиться к свойствам и параметрам настроек для безопасной работы алгоритма ИПЖ. Цели позволяют удостовериться, что все сконфигурировано правильно, что мы понимаем, что, как и почему делает система и что мы можем доверять ей.

Если вы **обновляете телефон**, то можете [экспортировать настройки](../Usage/Objectives#export-import-settings) чтобы сохранить прогресс в продвижении к целям. Ваш прогресс будет сохранен не только в прохождении целей, но и в настройках безопасности, таких как максимальный болюс и т. д. Если настройки не переносить, то движение к целям придется начинать заново. На всякий случай следует время от времени сохранять свои настройки. Подробности см. ниже.  

### Цель 1: Настройка визуализации и мониторинга, анализ базальной скорости и коэффициентов

* Выберите свой источник мониторинга ГК. См. [Источник ГК](../Configuration/BG-Source.md) для дополнительной информации.
* Выбираем нужную помпу в Конфигураторе (если к помпе нет драйвера, можно пользоваться виртуальной помпой) чтобы пома могла вести коммуникацию с AndroidAPS. При работе с [помпой Dana R ](../Configuration/DanaR-Insulin-Pump.md) следуйте отдельным инструкциям по привязке помпы к AndroidAPS.
* Следуйте инструкциям по настройке [Nightscout](../Installing-AndroidAPS/Nightscout.md) чтобы Nightscout мог получать и отображать данные ГК.

*Возможно, придется подождать следующего значения глюкозы крови, чтобы AndroidAPS принял его.*

### Цель 2: Начало на незамкнутом цикле

* Выбрать незамкнутый цикл либо в настройках либо нажав кнопку незамкнутого цикла в левом верхнем углу главного экрана.
* Задать все необходимые [Настройки](../Configuration/Preferences.md).
* Вручную активировать по крайней мере 20 предложений временного базала за период в 7 дней, ввести их в помпу и подтвердить в AndroidAPS. Убедитесь, что эти данные представлены в AndroidAPS и Nightscout.
* Включите [врем. цели](../Usage/temptarget.md) если необходимо. Используйте врем. цели для купирования гипогликемии чтобы предотвратить слишком сильные коррекции после гипо. 

### Objective 3: Understanding your open loop, including its temp basal recommendations

* Start to understand the thinking behind the temp basal recommendations by looking at the [determine basal logic](https://openaps.readthedocs.io/en/latest/docs/While%20You%20Wait%20For%20Gear/Understand-determine-basal.html) and both the forecast line in AndroidAPS homescreen/Nightscout and the summary of outputs from the calculations in your OpenAPS tab.

*You will want to set your target higher than usual until you are confident in the calculations and settings. The system allows a low target to be a minimum of 4 or maximum of 10, and a high target to be a minimum of 5 and maximum of 15. A temporary target as a single value can be anywhere in the range of 4 to 15. The target is the value that calculations are based on, and not the same as where you aim to keep your blood glucose values within. If your target is very wide (say, 3 or more mmol wide), you will often find because blood glucose is eventually predicted to be somewhere in that wide range not many fluctuating temporary basal rates are suggested. You may want to experiment with adjusting your targets to be a closer together range (say, 1 or less mmol wide), and observe how the behavior of your system changes as a result. You can view a wider range (green lines) on the graph for the values you aim to keep your blood glucose within by entering different values in Preference > Range for Visualisation.*

**Stop here if you are open looping with a virtual pump - do not click Verify at the end of this objective.**

### Objective 4: Starting to close the loop with Low Glucose Suspend

**Closed loop will not correct high bg values in objective 4 as it is limited to low glucose suspend.**

**High bg values have to be corrected manually by you!**

* Select Closed Loop either from Preferences, or by pressing and holding the Open Loop button in the top left of the home screen.
* Set your target range slightly higher than you usually aim for, just to be safe.
* Watch how temporary basals are active by viewing the blue basal text on the homescreen or the blue basal render on the homescreen graph.
* Ensure your settings have supported AndroidAPS to avoid having to treat a low glucose over a period of 5 days. If you are still having frequent or severe low glucose episodes then consider refining your DIA, basal, ISF and carb ratios.

*The system will override your maxIOB settings to zero, which means if blood glucose is dropping it can reduce basal for you, but if blood glucose is rising then it will only increase basal if the IOB is negative (from a previous Low Glucose Suspend), otherwise basal rates will remain the same as your selected profile. Возможны временные пики вслед за мерами против гипогликемии без возможности увеличить базу на откате._*

### Objective 5: Tuning the closed loop, raising max IOB above 0 and gradually lowering BG targets

* Raise your 'Maximum total IOB OpenAPS can’t go over' (in OpenAPS called 'max-iob') above 0 over a period of 1 day, the default recommendation is "average mealbolus + 3x max daily basal"(for SMB algorithm) or "3x max daily basal" (for older AMA algorithm) but you should slowly work up to this until you know your settings work for you (max daily basal = the maximum hourly value in any time segment of the day).
  
  This recommendation should be seen as a starting point. If you set to the 3x and you are seeing moves that push you to hard and fast then lower that number. If you are very resistant raise it a very little at a time.
  
  ![max daily basal](../images/MaxDailyBasal.png)

* Once confident on how much IOB suits your looping patterns then reduce your targets to your desired level.

### Objective 6: Adjust basals and ratios if needed, and then enable autosens

* You can use [autotune](https://openaps.readthedocs.io/en/latest/docs/Customize-Iterate/autotune.html) as a one off to check your basals remain accurate, or do a traditional basal test.
* Enable [autosens](../Usage/Open-APS-features.md) over a period of 7 days and watch the white line on the homescreen graph show how your sensitivity to insulin may be rising or falling as a result of exercise or hormones etc, and keep an eye in the OpenAPS report tab how AndroidAPS is adjusting the basals and/or targets accordingly.

*Don’t forget to record your looping in [this form](http://bit.ly/nowlooping) logging AndroidAPS as your type of DIY loop software, if you have not already done so.*

### Objective 7: Enabling additional oref0 features for daytime use, such as advanced meal assist (AMA)

* Now you should feel confident with how AndroidAPS works and what settings reflect your diabetes best
* Then over a period of 28 days you can try additional features that automate even more of the work for you such as the [advanced meal assist](../Usage/Open-APS-features#advanced-meal-assist-ama)

### Objective 8: Enabling additional oref1 features for daytime use, such as super micro bolus (SMB)

* You must read the [SMB chapter in this wiki](../Usage/Open-APS-features#super-micro-bolus-smb) and [chapter oref1 in openAPSdocs](https://openaps.readthedocs.io/en/latest/docs/Customize-Iterate/oref1.html) to understand how SMB works, especially what's the idea behind zero-temping.
* Then you ought to [rise maxIOB](../Usage/Open-APS-features#maximum-total-iob-openaps-cant-go-over-openaps-max-iob) to get SMBs working fine. maxIOB now includes all IOB, not just added basal. That is, if given a bolus of 8 U for a meal and maxIOB is 7 U, no SMBs will be delivered until IOB drops below 7 U. A good start is maxIOB = average mealbolus + 3x max daily basal (max daily basal = the maximum hourly value in any time segment of the day - see [objective 5](../Usage/Objectives#objective-5-tuning-the-closed-loop-raising-max-iob-above-0-and-gradually-lowering-bg-targets) for an illustration)
* min_5m_carbimpact default in absorption settings has changed from 3 to 8 going from AMA to SMB. Если вы переходите с AMA на SMB, то вам нужно изменить его вручную

## Export & import settings

* Выполнить **Экспорт настроек** на вашем старом телефоне
  
  * Сэндвич-меню (в верхнем левом углу экрана)
  * Тех. обслуживание
  * Экспорт настроек
  * File location will be shown
    
    ![Экспорт настроек AAPS](../images/AAPS_ExportSettings.png)

* **Transfer** settings from old to new phone using the file location shown during export

* **Установите AndroidAPS** на новом телефоне.
* **Выполните импорт настроек** на вашем новом телефоне 
  * Сэндвич-меню (в верхнем левом углу экрана)
  * Тех. обслуживание
  * Выполните импорт настроек
* **Note for Dana RS users:** 
  * Поскольку настройки подключения помпы также переносятся новый телефон, AAPS на новом телефоне уже будет "знать" помпу и не запустит сканирование bluetooth. Please pair new phone and pump manually.