---
title: Mpgo.exe (strumento per l'ottimizzazione guidata da profilo gestito)
ms.date: 03/30/2017
helpviewer_keywords:
- Mpgo.exe
- training scenarios, generating profiles with
- Managed Profile Guided Optimization Tool
- Ngen.exe
- Ngen.exe, profilers and native images
ms.assetid: f6976502-a000-4fbe-aaf5-a7aab9ce4ec2
ms.openlocfilehash: 0052475697dae2c3ad891db18d300b5ec08a7e62
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180353"
---
# <a name="mpgoexe-managed-profile-guided-optimization-tool"></a>Mpgo.exe (strumento per l'ottimizzazione guidata da profilo gestito)

Lo strumento per l'ottimizzazione guidata da profilo gestito (Mpgo.exe) è uno strumento da riga di comando che usa scenari comuni dell'utente finale per ottimizzare gli assembly di immagini native creati dal [generatore di immagini native (Ngen.exe)](ngen-exe-native-image-generator.md). Attraverso questo strumento è possibile eseguire scenari di training che generano dati di profilatura, Il [generatore di immagini native (Ngen.exe)](ngen-exe-native-image-generator.md) usa questi dati per ottimizzare gli assembly di applicazioni di immagini native generati. Uno scenario di training è un'esecuzione di test di un uso previsto dell'applicazione. Mpgo.exe è disponibile in Visual Studio Ultimate 2012 e versioni successive. A partire da Visual Studio 2013, puoi anche usare Mpgo.exe per ottimizzare le app di Windows 8.x Store.  
  
L'ottimizzazione PGO migliora i tempi di avvio dell'applicazione, l'utilizzo della memoria (dimensioni del working set) e la velocità effettiva raccogliendo dati dagli scenari di prova e utilizzandoli per ottimizzare il layout delle immagini native.  
  
Quando si verificano problemi di prestazioni relativi al tempo di avvio e alle dimensioni del working set per gli assembly di linguaggio intermedio (IL), è consigliabile innanzitutto utilizzare Ngen.exe per eliminare i costi della compilazione just-in-time (JIT) e per facilitare la condivisione del codice. Se sono necessari miglioramenti aggiuntivi, è possibile utilizzare Mpgo.exe per ottimizzare ulteriormente l'applicazione. È possibile utilizzare i dati delle prestazioni degli assembly di immagini native non ottimizzati come base di riferimento per valutare l'incremento delle prestazioni. L'utilizzo di Mpgo.exe può produrre tempi di avvio a freddo più rapidi e un working set di dimensioni più ridotte. Mpgo.exe aggiunge informazioni agli assembly IL utilizzati da Ngen.exe per creare assembly di immagini native ottimizzati. Per altre informazioni, vedere il post [Improving Launch Performance for your Desktop Applications](https://devblogs.microsoft.com/dotnet/improving-launch-performance-for-your-desktop-applications/) (Miglioramento delle prestazioni di avvio per le applicazioni desktop) nel blog di .NET.  
  
Viene installato automaticamente con Visual Studio. Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7) con credenziali di amministratore e digitare quanto segue. Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).  
  
Per le app desktop:  
  
```console  
mpgo –Scenario <command> [-Import <directory>] –AssemblyList <assembly1>  <assembly2> ... -OutDir <directory> [options]  
```  
  
Per le app di Windows 8.x Store:  
  
## <a name="syntax"></a>Sintassi  
  
```console  
mpgo –Scenario <packageName> -AppID <appId> -Timeout <seconds>  
```  
  
## <a name="parameters"></a>Parametri  
 Gli argomenti di Mpgo.exe non sono soggetti a distinzione tra maiuscole e minuscole. I comandi sono preceduti da un trattino.  
  
> [!NOTE]
> È possibile utilizzare `–Scenario` o `–Import` come comando obbligatorio, ma non entrambi. Nessuno dei parametri obbligatori viene usato se si specifica l'opzione `–Reset`.

|Parametro obbligatorio.|Descrizione|
|------------------------|-----------------|
|`-Scenario`\< *comando*><br /><br /> -oppure-<br /><br /> `-Scenario`\< *packageName (nomepacchetto)*><br /><br /> -oppure-<br /><br /> `-Import`\< *directory*>|Per le app desktop, usare `–Scenario` per specificare il comando per eseguire l'applicazione che si desidera ottimizzare, inclusi gli eventuali argomenti della riga di comando. Racchiudere *comando* in tre set di virgolette doppie se si specifica un percorso che include spazi; ad esempio: `mpgo.exe -scenario """C:\My App\myapp.exe""" -assemblylist """C:\My App\myapp.exe""" -outdir "C:\optimized files"`. Non usare le virgolette doppie; non funzioneranno correttamente se *comando* include spazi.<br /><br /> -oppure-<br /><br /> Per le app di Windows `–Scenario` 8.x Store, usalo per specificare il pacchetto per il quale vuoi generare le informazioni sul profilo. Se si specifica il nome visualizzato del pacchetto o il nome di famiglia del pacchetto anziché il nome completo del pacchetto, Mpgo.exe selezionerà il pacchetto che corrisponde al nome immesso se è presente solo una corrispondenza. Se più pacchetti corrispondono al nome specificato, verrà richiesto di scegliere un pacchetto.<br /><br /> -oppure-<br /><br /> Utilizzare `-Import` per specificare che i dati di ottimizzazione derivati da assembly precedentemente ottimizzati devono essere utilizzati per ottimizzare gli assembly in `-AssemblyList`. *directory* specifica la directory che contiene i file ottimizzati precedentemente. Gli assembly specificati in `–AssemblyList` o `–AssemblyListFile` sono le nuove versioni di assembly da ottimizzare usando i dati dai file importati. L'utilizzo dei dati di ottimizzazione da versioni precedenti degli assembly consente di ottimizzare le versioni più recenti senza rieseguire lo scenario.  Tuttavia, se gli assembly importati e di destinazione includono codice notevolmente diverso, i dati di ottimizzazione saranno inefficaci. I nomi degli assembly specificati in `–AssemblyList` o `–AssemblyListFile` devono essere inclusi nella directory specificata da `–Import`*directory*. Racchiudere *directory* in tre set di virgolette doppie se si specifica un percorso che include spazi.<br /><br /> È necessario specificare il parametro `–Scenario` o `–Import`, ma non entrambi i parametri.|
|`-OutDir`\< *directory*>|Directory in cui inserire gli assembly ottimizzati. Se esiste già un assembly nella directory di output, viene creata una nuova copia e viene aggiunto un numero di indice al nome, ad esempio *nomeassembly*-1.exe. Racchiudere *directory* in virgolette doppie se si specifica un percorso che contiene spazi.|
|`-AssemblyList`\< *assemblaggio1 assembly2 ...*><br /><br /> -oppure-<br /><br /> `-AssemblyListFile`\< *file*>|Elenco di assembly (inclusi file .exe e .dll), separati da spazi, di cui si desidera raccogliere informazioni riguardanti il profilo. È possibile specificare `C:\Dir\*.dll` o `*.dll` per selezionare tutti gli assembly nella directory di lavoro definita o corrente. Per ulteriori informazioni, vedere le sezione Note.<br /><br /> -oppure-<br /><br /> File di testo che contiene l'elenco di assembly di cui si desidera raccogliere informazioni sul profilo, un assembly per riga. Se il nome dell'assembly inizia con un trattino (-), utilizzare un elenco di file di assembly o rinominare l'assembly.|
|`-AppID`\< *appId (AppId)*>|ID dell'applicazione nel pacchetto specificato. Se si usa il carattere jolly (\*), Mpgo.exe proverà a enumerare gli IDapp nel pacchetto ed eseguirà il fallback a \<*package_family_name*>!App se non riesce. Se si specifica una stringa preceduta da un punto esclamativo (!), verrà concatenato il nome della famiglia del pacchetto con l'argomento fornito.|
|`-Timeout`\< *secondi*>|Periodo di tempo per consentire l'esecuzione dell'app Windows 8.x Store prima della chiusura dell'app.|

|Parametro facoltativo|Descrizione|
|------------------------|-----------------|
|`-64bit`|Instrumenta gli assembly per i sistemi a 64 bit.  È necessario specificare questo parametro per gli assembly a 64 bit, anche se l'assembly si dichiara come a 64 bit.|
|`-ExeConfig`\< *nome file*>|Specifica il file di configurazione utilizzato dallo scenario per fornire informazioni sulla versione e sul caricatore.|
|`-f`|Forza l'inclusione dei dati di profilo in un assembly binario, anche se è firmato.  Se l'assembly è firmato, è necessario firmarlo nuovamente; in caso contrario, l'assembly non verrà caricato ed eseguito.|
|`-Reset`|Reimposta l'ambiente per assicurare che una sessione di profilatura interrotta non influisca sugli assembly ed esce. L'ambiente viene reimpostato per impostazione predefinita prima e dopo una sessione di profilatura.|
|`-Timeout`\< *tempo in secondi*>|Specifica la durata della profilatura in secondi. Utilizzare un valore leggermente superiore dei tempi di avvio osservati per le applicazioni GUI. Alla fine del periodo di timeout, i dati di profilo vengono registrati anche se l'applicazione continua l'esecuzione. Se non si imposta questa opzione, la profilatura continuerà fino alla chiusura dell'applicazione, momento nel quale i dati verranno registrati.|
|`-LeaveNativeImages`|Specifica che le immagini native instrumentate non devono essere rimosse dopo l'esecuzione dello scenario. Questa opzione viene utilizzata principalmente quando si esegue l'applicazione specificata per lo scenario, perché impedisce la nuova creazione di immagini native per le esecuzioni successive di Mpgo.exe. Dopo aver completato l'esecuzione dell'applicazione, possono rimanere immagini native orfane nella cache se si specifica questa opzione. In questo caso, eseguire Mpgo.exe con lo stesso scenario ed elenco di assembly e utilizzare il parametro`–RemoveNativeImages` per rimuovere queste immagini native.|
|`-RemoveNativeImages`|Esegue la pulizia dopo un'esecuzione in cui `–LeaveNativeImages` è stato specificato. Se si specifica `-RemoveNativeImages`, eventuali argomenti tranne `-64bit` e `–AssemblyList` vengono ignorati da Mpgo.exe e lo strumento viene chiuso dopo avere rimosso tutte le immagini native instrumentate.|

## <a name="remarks"></a>Osservazioni
 È possibile usare sia `–AssemblyList` che `- AssemblyListFile` più volte nella riga di comando.

 Se non si specificano nomi di percorso completi quando si specificano gli assembly, Mpgo.exe cerca nella directory corrente. Se si specifica un percorso errato, Mpgo.exe visualizza un messaggio di errore, ma continua a generare dati per altri assembly. Se si specifica un assembly che non viene caricato durante lo scenario di prova, i dati di prova non vengono generati per tale assembly.

 Se un assembly nell'elenco è presente nella Global Assembly Cache, non verrà aggiornato con le informazioni sul profilo.  Rimuoverlo dalla Global Assembly Cache per raccogliere informazioni sul profilo.

 L'utilizzo di Ngen.exe e di Mpgo.exe è consigliato solo per le applicazioni gestite di grandi dimensioni, poiché il vantaggio offerto dalle immagini native precompilate è in genere significativo solo quando elimina una quantità notevole di attività di compilazione JIT in fase di esecuzione. L'esecuzione di Mpgo.exe su applicazioni di tipo "Hello World" che non fanno un uso elevato del working set non offre alcun vantaggio e Mpgo.exe può anche non riuscire a raccogliere i dati di profilo.

> [!NOTE]
> Ngen.exe e Mpgo.exe non sono consigliati per le applicazioni ASP.NET e i servizi Windows Communication Foundation (WCF).  
  
## <a name="to-use-mpgoexe"></a>Per utilizzare Mpgo.exe  
  
1. Utilizzare un computer con Visual Studio Ultimate 2012 e l'applicazione installata.  
  
2. Eseguire Mpgo.exe come amministratore con i parametri necessari.  Vedere la sezione successiva per alcuni comandi di esempio.  
  
     Gli assembly Intermediate Language (IL) ottimizzati vengono creati nella cartella specificata dal parametro `–OutDir` (negli esempi si tratta della cartella `C:\Optimized`).  
  
3. Sostituire gli assembly IL utilizzati per Ngen.exe con i nuovi assembly IL che contengono le informazioni sul profilo dalla directory specificata da `–OutDir`.  
  
4. Il programma di installazione dell'applicazione (che usa le immagini fornite da Mpgo.exe) installerà le immagini native ottimizzate.  
  
## <a name="suggested-workflow"></a>Flusso di lavoro suggerito  
  
1. Creare un set di assembly IL ottimizzati usando Mpgo.exe con il parametro `–Scenario`.  
  
2. Archiviare gli assembly IL ottimizzati nel controllo del codice sorgente.  
  
3. Nel processo di compilazione, chiamare Mpgo.exe con il parametro `–Import` come passaggio di post-compilazione per generare immagini IL ottimizzate da passare a Ngen.exe.  
  
 Questo processo assicura che tutti gli assembly abbiano dati di ottimizzazione. Se si archiviano assembly ottimizzati aggiornati (passaggi 1 e 2) più spesso, le prestazioni risulteranno più coerenti durante lo sviluppo del prodotto.  
  
## <a name="using-mpgoexe-from-visual-studio"></a>Utilizzo di Mpgo.exe da Visual Studio  
 È possibile eseguire Mpgo.exe da Visual Studio (vedere l'articolo [Procedura: Specificare eventi di compilazione (C#)](/visualstudio/ide/how-to-specify-build-events-csharp)) con le restrizioni seguenti:  
  
- Non è possibile usare percorsi tra virgolette con la barra finale, perché anche le macro di Visual Studio usano la barra finale per impostazione predefinita (Ad esempio, `–OutDir "C:\Output Folder\"` non è valido.) Per aggirare questa restrizione, è possibile eseguire l'escape della barra finale. Ad esempio, usare invece `-OutDir "$(OutDir)\"`.  
  
- Per impostazione predefinita, Mpgo.exe non si trova nel percorso di compilazione di Visual Studio. È necessario aggiungere il percorso a Visual Studio o specificare il percorso completo sulla riga di comando di Mpgo. È possibile utilizzare il parametro `–Scenario` o `–Import` nell'evento di post-compilazione in Visual Studio. Il processo tipico consiste tuttavia nell'usare `–Scenario` richiesto una sola volta al Prompt dei comandi per gli sviluppatori per Visual Studio e quindi usare `–Import` per aggiornare gli assembly ottimizzati dopo ogni compilazione; ad esempio: `"C:\Program Files\Microsoft Visual Studio 11.0\Team Tools\Performance Tools\mpgo.exe" -import "$(OutDir)tmp" -assemblylist "$(TargetPath)" -outdir "$(OutDir)\"`.  
  
<a name="samples"></a>
## <a name="examples"></a>Esempi  
 Il seguente comando Mpgo.exe eseguito al Prompt dei comandi per gli sviluppatori per Visual Studio ottimizza un'applicazione fiscale:  
  
```console  
mpgo –scenario "C:\MyApp\MyTax.exe /params par" –AssemblyList Mytax.dll MyTaxUtil2011.dll –OutDir C:\Optimized –TimeOut 15  
```  
  
 Il seguente comando Mpgo.exe ottimizza un'applicazione audio:  
  
```console  
mpgo –scenario "C:\MyApp\wav2wma.exe –input song1.wav –output song1.wma" –AssemblyList transcode.dll –OutDir C:\Optimized –TimeOut 15  
```  
  
 Il seguente comando Mpgo.exe utilizza i dati degli assembly precedentemente ottimizzati per ottimizzare le versioni più recenti degli assembly:  
  
```console  
mpgo.exe -import "C:\Optimized" -assemblylist "C:\MyApp\MyTax.dll" "C:\MyApp\MyTaxUtil2011.dll" -outdir C:\ReOptimized  
```  
  
## <a name="see-also"></a>Vedere anche

- [Ngen.exe (generatore di immagini native)](ngen-exe-native-image-generator.md)
- [Prompt dei comandi](developer-command-prompt-for-vs.md)
- [Improving Launch Performance for your Desktop Applications](https://devblogs.microsoft.com/dotnet/improving-launch-performance-for-your-desktop-applications/) (Miglioramento delle prestazioni di avvio per le applicazioni desktop)
- [Panoramica dei miglioramenti delle prestazioni in .NET 4.5](https://docs.microsoft.com/archive/msdn-magazine/2012/april/clr-an-overview-of-performance-improvements-in-net-4-5)
