Синхронизација на концерт
======

На еден концерт потребно е за секој изведувач да се формираат три групи од пратечки групи составени од тенори и баритони, 
по што сите заедно настапуваат. По завршувањето на настапот на започнува гласањето за изедбата. 

При изведбата, прво паралелно се формираат трите пратечки групи (секоја составена од по еден тенор и еден баритон), 
за потоа да го започнат настапот со изедувачот. На концертот има голем број на изведувачи, тенори и баритони. Настапите 
се еден по еден.
 
Вашата задача е да ги имплементирате методите `execute()` од класите `Tenor`, `Baritone` и `Performer`, кои се наоѓаат 
во фајлот `Concert.java`. При решавањето можете да користите семафори и монитори по ваша желба и нивната иницијализација 
треба да ја направите во `init()` методот.

Потребно е да го синхронизирате настапот со користење на следните функции:

 - `state.formBackingVocals()` - Кажува дека може да се формира групата на придружни вокали
    - Се повиква само кај тенорите и баритоните.
    - Треба да се повика истовремено од тенорот и баритонот кои  ја формираат групата. 
    - Треба трите пратечки групи да се креираат паралелно (во спротивен случај ќе добиете порака за грешка). 
    - При повикот, тенорите треба да се сигурни дека има присутен баритон и обратно. 
    - Доколку методот истовремено го повикаат повеќе од три пара тенори и баритони, ќе добиете порака за грешка.
 - `state.perform()` - Кажува дека може да започне настапот
    - Треба да се повика од сите присутни (изведувачот и трите пратечки групи). 
    - Доколку претходно не се формирани трите пратечки групи, ќе добиете порака за грешка.
    - Доколку методот е повикан од повеќе од 3 тенори, 3 баритони и 1 изведувач, ќе добиете порака за грешка. 
 - `state.vote()` - Го симболизира гласањето за настапот
    - Се повикува од изведувачот.
    - Доколку не завршил настапот ќе добиете порака за грешка.
    - Доколку не се присутни сите што настапиле, ќе добиете порака за грешка.
    
За решавање на задачата, преземете го проектот со клик на копчето `Starter file`, отпакувајте го и отворете го со 
IntelliJ IDEA, Eclipse или Netbeans.  



При стартувањето на класата, сценариото ќе се повика 10 пати, со креирање на голем број инстанци од класите `Tenor`, 
`Baritone` и `Performer` и паралелно само еднаш ќе се повика нивниот `execute()` метод. 

Решението треба да се прикачи според инструкциите подолу.