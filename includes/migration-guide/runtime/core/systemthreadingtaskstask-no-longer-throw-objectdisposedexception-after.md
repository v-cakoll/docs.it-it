### <a name="systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a>System.Threading.Tasks.Task non genera più ObjectDisposedException dopo l'eliminazione dell'oggetto

|   |   |
|---|---|
|Dettagli|Ad eccezione di <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle>, i metodi <xref:System.Threading.Tasks.Task?displayProperty=name> non generano più un'eccezione <xref:System.ObjectDisposedException?displayProperty=name> successivamente all'eliminazione dell'oggetto. Questa modifica supporta l'uso di attività memorizzate nella cache. Ad esempio, un metodo può restituire un'attività memorizzata nella cache per rappresentare un'operazione già completata anziché allocare una nuova attività. Ciò non è possibile nelle versioni precedenti di .NET Framework, perché qualsiasi utente dell'attività può rimuoverla e renderla così inutilizzabile.|
|Suggerimento|Tenere presente che i metodi Task potrebbero non generare più eccezioni <xref:System.ObjectDisposedException?displayProperty=name> nei casi in cui viene eliminato l'oggetto. Se un'app dipende da questa eccezione per venire a conoscenza dell'eliminazione di un'attività, è necessario aggiornarla in modo che controlli in modo esplicito lo stato dell'attività tramite <xref:System.Threading.Tasks.Task.Status>.|
|Ambito|Secondario|
|Versione|4.5|
|Tipo|Runtime|

