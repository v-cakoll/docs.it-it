### <a name="resolveassemblyreference-task-now-warns-of-dependencies-with-the-wrong-architecture"></a>L'attiva ResolveAssemblyReference genera ora avvisi in caso di dipendenze con l'architettura non corretta

|   |   |
|---|---|
|Dettagli|L'attività genera un avviso, MSB3270, che indica la mancata corrispondenza di un riferimento o di una delle sue dipendenze all'architettura dell'app. Questa situazione si verifica ad esempio se un'app compilata con l'opzione <code>AnyCPU</code> include un riferimento x86. Uno scenario di questo tipo potrebbe provocare un errore dell'app in fase di esecuzione (nel caso descritto, se l'app viene distribuita come processo x64).|
|Suggerimento|Le possibili conseguenze riguardano le aree seguenti:<ul><li>La ricompilazione genera avvisi che non venivano visualizzati quando l'app veniva compilata con una versione precedente di MSBuild. Tuttavia, dal momento che l'avviso identifica una possibile fonte di errore di runtime, deve essere analizzato e affrontato.</li><li>Se gli avvisi vengono considerati errori, la compilazione dell'app non verrà completata.</li></ul>|
|Ambito|Secondario|
|Versione|4.5.1|
|Tipo|Ridestinazione|

