### <a name="change-in-behavior-in-data-definition-language-ddl-apis"></a>Modifica del comportamento nelle API DDL (Data Definition Language)

|   |   |
|---|---|
|Dettagli|Il comportamento delle API DDL quando si specifica AttachDBFilename è cambiato come segue:<ul><li>Le stringhe di connessione non devono specificare un valore Initial Catalog. In precedenza, erano necessari sia AttachDBFilename che Initial Catalog.</li><li>Se vengono specificati sia AttachDBFilename che Initial Catalog e il file MDF indicato esiste, il metodo ObjectContext.DatabaseExists restituisce true. In precedenza, restituiva false.</li><li>Se vengono specificati sia AttachDBFilename che Initial Catalog e il file MDF indicato esiste, la chiamata al metodo ObjectContext.DeleteDatabase elimina i file.</li><li>Se ObjectContext.DeleteDatabase viene chiamato quando la stringa di connessione specifica un valore AttachDBFilename con un file MDF e un valore Initial Catalog inesistenti, il metodo genera un'eccezione InvalidOperationException. In precedenza, generava un'eccezione SqlException.</li></ul>|
|Suggerimento|Queste modifiche semplificano la creazione di strumenti e applicazioni che usano le API DDL. Tali modifiche possono influire sulla compatibilità delle applicazioni negli scenari seguenti:<ul><li>L'utente scrive codice che esegue un comando DROP DATABASE direttamente anziché chiamando ObjectContext.DeleteDatabase se ObjectContext.DatabaseExists restituisce true. Questa operazione interrompe il codice esistente se il database non è collegato ma il file MDF esiste.</li><li>L'utente scrive codice che prevede che il metodo ObjectContext.DeleteDatabase generi un'eccezione SqlException invece di un'eccezione InvalidOperationException se il valore Initial Catalog e il file MDF non esistono.</li></ul>|
|Ambito|Secondario|
|Versione|4.5|
|Tipo|Runtime|

