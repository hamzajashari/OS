Kindergarten Show Problem
===========================
На претстава во градинка на која учествуваат 24 дечиња има само една бина на која има место за 6 учесници. Презентацијата на учесниците 
на бината се одвива во повеќе циклуси, каде во секој циклус на бината својата точка ја изведуваат 4 групи на учесници, една по една. 
Групите се составуваат произволно,според тоа дали има место на бината и како пристигнале учесниците.
Претставата се одвива според следните правила: 

 - учесниците може да излезат на бината само доколку има слободни места
 - кога ќе се соберат 6 учесници на бината, започнуваат со својата точка
 - откако ќе завршат со точката, секој од учесниците чека да завршат останатите групи, пред да се обиде повторно да се качи на бината 
 - нови играчи не смеат да влезат додека не излезат оние што претходно играле
 - потоа сценариото може да започне од почеток

Вашата задача е да го синхронизирате претходното сценарио.

Во почетниот код кој е даден, дефинирана е класа `Child`, која го симболизира однесувањето на учесниците на претставата. 
Има 20 инстанци од класата `Child` кај кои методот `execute()` се повикува онолку пати колку што има циклуси на карневалот. 

Во имплементацијата, треба да ги користите следните методи од веќе дефинираната променлива `state`:

 - `state.participantEnter()`
    - Го симболизира влегувањето на учесникот на бината.
    - Се повикува од сите учесници.  
    - Доколку ист учесник го повика методот во рамките на ист циклус, ќе повика исклучок.
    - Доколку се повика кога бината е полна, ќе фрли исклучок.
    - Доколку се повика пред претходната група да заврши со презентирањето(`state.endGroup()`), ќе фрли исклучок.  
 - `state.present()`
    - Го симболизира процесот на презентирање на учесниците.
    - Се повикува од сите учесници. 
    - Доколку процесот на презентирање не се извршува паралелно, ќе добиете порака за грешка.
    - Доколку бината не е пополнета (нема точно 6 присутни учесници), ќе фрли исклучок.
 - `state.endGroup()`
    - Означува дека сите учесници од групата завршиле со презентирањето и може да излезат од бината.
    - Се повикува само од еден учесник.
    - Доколку во моменот на повикување има учесници кои се' уште се присутни на бината, ќе фрли исклучок.
 - `state.endCycle()`
    - Означува дека сите групи и учесници завршиле со презентирањето и може да започне следниот циклус.
    - Се повикува само од еден учесник.
    - Доколку во моменот на повикување има учесници кои се' уште не завршиле, ќе фрли исклучок.

Претходно назначените методи служат за проверка на точноста на сценариото и не смеат да бидат променети и мора да бидат повикани.

За решавање на задачата, преземете го проектот со клик на копчето `Starter file`, отпакувајте го и отворете го со Eclipse или Netbeans.

Вашата задача е да го имплементирате методот `execute()` од класата `Child`, која се наоѓа во датотеката `KindergartenShow.java`. 
При решавањето може да се користат семафори и монитори по желба и нивната иницијализација да се направи во `init()` методот.

**Напомена:** Пораките и грешките кои се прикажуваат при извршувањето служат за детектирање на нерегуларности во сценариото. 
Проблемите Race-condition и одредени ситуации на Deadlock не може да се детектираат и прикажат. 
Поради конкурентниот пристап за логирањето, можно е некои од пораките да не се на позицијата каде што треба да се. 
Токму затоа, овие пораки користете ги само како информација. 
