### <a name="persian-calendar-now-uses-the-hijri-solar-algorithm"></a>Il calendario persiano ora usa l'algoritmo solare Hijri

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.6, la classe <xref:System.Globalization.PersianCalendar?displayProperty=name> usa l'algoritmo solare Hijri. La conversione di date tra il calendario <xref:System.Globalization.PersianCalendar?displayProperty=name> e altri calendari può produrre risultati leggermente diversi a partire da .NET Framework 4.6 per le date precedenti al 1800 o successive al 2023 (calendario gregoriano). Inoltre, <xref:System.Globalization.PersianCalendar.MinSupportedDateTime> è ora <code>March 22, 0622 instead of March 21, 0622</code>.|
|Suggerimento|Tenere presente che alcune date precedenti o successive potrebbero essere leggermente diverse quando si usa PersianCalendar in .NET 4.6. Inoltre, quando si serializzano le date tra processi che possono essere eseguiti in versioni diverse di .NET Framework, evitare di archiviarle come stringhe di data PersianCalendar, perché tali valori potrebbero essere diversi.|
|Ambito|Secondario|
|Versione|4.6|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Globalization.PersianCalendar?displayProperty=nameWithType></li></ul>|

