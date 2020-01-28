---
title: Distribuire .NET per Apache Spark Worker e i file binari delle funzioni definite dall'utente
description: Informazioni su come distribuire .NET per Apache Spark di lavoro e binari di funzioni definite dall'utente.
ms.date: 01/21/2019
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: f9197ca3cf8066f0849ebbe70d7757c9035d02f6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76748531"
---
# <a name="deploy-net-for-apache-spark-worker-and-user-defined-function-binaries"></a>Distribuire .NET per Apache Spark Worker e i file binari delle funzioni definite dall'utente

In questa procedura vengono fornite istruzioni generali su come distribuire .NET per i file binari di Apache Spark Worker e di funzioni definite dall'utente. Vengono fornite informazioni sulle variabili di ambiente da configurare, oltre ad alcuni parametri di uso comune per l'avvio di applicazioni con `spark-submit`.

## <a name="configurations"></a>Configurazioni
Nelle configurazioni sono illustrate le impostazioni generali per le variabili di ambiente e i parametri per distribuire .NET per i file binari di Apache Spark Worker e di funzioni definite dall'utente.

### <a name="environment-variables"></a>Variabili di ambiente
Quando si distribuiscono i ruoli di lavoro e si scrivono UDF, è possibile che sia necessario impostare alcune variabili di ambiente di uso comune: 

| Variabile di ambiente         | Descrizione
| :--------------------------- | :---------- 
| DOTNET_WORKER_DIR            | Percorso in cui è stato generato il file binario <code>Microsoft.Spark.Worker</code>.</br>Viene usato dal driver Spark e verrà passato agli esecutori Spark. Se questa variabile non è impostata, gli esecutori Spark eseguiranno la ricerca nel percorso specificato nella variabile di ambiente <code>PATH</code>.</br>_ad esempio, "C:\bin\Microsoft.Spark.Worker"_
| DOTNET_ASSEMBLY_SEARCH_PATHS | Percorsi delimitati da virgole in cui <code>Microsoft.Spark.Worker</code> caricherà gli assembly.</br>Si noti che se un percorso inizia con ".", la directory di lavoro verrà anteposta. Se è in **modalità Yarn**, "." rappresenterà la directory di lavoro del contenitore.</br>_ad esempio, "C:\Users\\&lt;nome utente&gt;\\&lt;mysparkapp&gt;\bin\Debug\\&lt;DotNet versione&gt;"_
| DOTNET_WORKER_DEBUG          | Se si vuole <a href="https://github.com/dotnet/spark/blob/master/docs/developer-guide.md#debugging-user-defined-function-udf">eseguire il debug di una funzione definita dall'utente</a>, impostare questa variabile di ambiente su <code>1</code> prima di eseguire <code>spark-submit</code>.

### <a name="parameter-options"></a>Opzioni parametro
Quando l'applicazione Spark è in [bundle](https://spark.apache.org/docs/latest/submitting-applications.html#bundling-your-applications-dependencies), è possibile avviarla usando `spark-submit`. Nella tabella seguente vengono illustrate alcune delle opzioni di uso comune: 

| Nome parametro        | Descrizione
| :---------------------| :---------- 
| --Class               | Il punto di ingresso per l'applicazione.</br>_ad esempio, org. Apache. Spark. deploy. dotnet. DotnetRunner_
| --Master              | <a href="https://spark.apache.org/docs/latest/submitting-applications.html#master-urls">URL Master</a> per il cluster.</br>_ad esempio Yarn_
| --Deploy-Mode         | Indica se distribuire il driver nei nodi di lavoro (<code>cluster</code>) o localmente come client esterno (<code>client</code>).</br>Valore predefinito: <code>client</code>
| --conf                | Proprietà di configurazione di Spark arbitraria nel formato <code>key=value</code>.</br>_ad esempio Spark. Yarn. appMasterEnv. DOTNET_WORKER_DIR = .\worker\Microsoft.Spark.Worker_
| --file               | Elenco di file delimitati da virgole da inserire nella directory di lavoro di ogni Executor.<br/><ul><li>Si noti che questa opzione è applicabile solo per la modalità Yarn.</li><li>Supporta la specifica di nomi file con # simile a Hadoop.</br></ul>_ad esempio <code>myLocalSparkApp.dll#appSeen.dll</code>. L'applicazione deve usare il nome come <code>appSeen.dll</code> per fare riferimento <code>myLocalSparkApp.dll</code> durante l'esecuzione su YARN._</li>
| --archivi          | Elenco delimitato da virgole di archivi da estrarre nella directory di lavoro di ogni Executor.</br><ul><li>Si noti che questa opzione è applicabile solo per la modalità Yarn.</li><li>Supporta la specifica di nomi file con # simile a Hadoop.</br></ul>_ad esempio <code>hdfs://&lt;path to your worker file&gt;/Microsoft.Spark.Worker.zip#worker</code>. Il file zip verrà copiato ed estratto nella cartella <code>worker</code>._</li>
| applicazione-jar       | Percorso di un file jar in bundle che include l'applicazione e tutte le dipendenze.</br>_ad esempio, hdfs://&lt;percorso del file jar&gt;/Microsoft-Spark-&lt;versione&gt;. jar_
| argomenti dell'applicazione | Argomenti passati al metodo principale della classe principale, se presenti.</br>_ad esempio, hdfs://&lt;il percorso dell'app&gt;/&lt;l'app&gt;. zip &lt;il nome dell'app&gt; &lt;argomenti dell'app&gt;_

> [!NOTE]
> Specificare tutti i `--options` prima `application-jar` quando si avviano le applicazioni con `spark-submit`. in caso contrario, verranno ignorati. Per altre informazioni, vedere [`spark-submit` Options](https://spark.apache.org/docs/latest/submitting-applications.html) ed [esecuzione di Spark su Yarn Details](https://spark.apache.org/docs/latest/running-on-yarn.html).

## <a name="frequently-asked-questions"></a>Domande frequenti
### <a name="when-i-run-a-spark-app-with-udfs-i-get-a-filenotfoundexception-error-what-should-i-do"></a>Quando si esegue un'app Spark con funzioni definite dall'utente, viene generato un errore ' FileNotFoundException '. Come si deve procedere?
> **Errore:** [errore] [TaskRunner] [0] ProcessStream () non riuscito con eccezione: System. io. FileNotFoundException: assembly ' MySparkApp, Version = 1.0.0.0, Culture = neutral, PublicKeyToken = null ' file non trovato:' mySparkApp. dll '

**Risposta:** Verificare che la variabile di ambiente `DOTNET_ASSEMBLY_SEARCH_PATHS` sia impostata correttamente. Deve essere il percorso che contiene il `mySparkApp.dll`.

### <a name="after-i-upgraded-my-net-for-apache-spark-version-and-reset-the-dotnet_worker_dir-environment-variable-why-do-i-still-get-the-following-ioexception-error"></a>Dopo l'aggiornamento di .NET per Apache Spark versione e la reimpostazione della variabile di ambiente `DOTNET_WORKER_DIR`, perché viene comunque riportato il seguente errore `IOException`?
> **Errore:** Attività persa 0,0 nella fase 11,0 (TID 24, localhost, driver Executor): Java. io. IOException: non è possibile eseguire il programma "Microsoft. Spark. Worker. exe": errore CreateProcess = 2, il sistema non riesce a trovare il file specificato.

**Risposta:** Provare a riavviare prima la finestra di PowerShell (o altre finestre di comando) in modo da poter usare i valori delle variabili di ambiente più recenti. Avviare quindi il programma.

### <a name="after-submitting-my-spark-application-i-get-the-error-systemtypeloadexception-could-not-load-type-systemruntimeremotingcontextscontext"></a>Dopo aver inviato l'applicazione Spark, viene generato l'errore `System.TypeLoadException: Could not load type 'System.Runtime.Remoting.Contexts.Context'`.
> **Errore:** [errore] [TaskRunner] [0] ProcessStream () non riuscito con eccezione: System. TypeLoadException: Impossibile caricare il tipo ' System. Runtime. Remoting. Contexts. Context ' dall'assembly ' mscorlib, Version = 4.0.0.0, Culture = neutral, PublicKeyToken =.. .'.

**Risposta:** Controllare la versione `Microsoft.Spark.Worker` in uso. Sono disponibili due versioni: **.NET Framework 4.6.1** e **.NET Core 2.1. x**. In questo caso, è consigliabile usare `Microsoft.Spark.Worker.net461.win-x64-<version>` (che è possibile [scaricare](https://github.com/dotnet/spark/releases)) poiché `System.Runtime.Remoting.Contexts.Context` è solo per .NET Framework.

### <a name="how-do-i-run-my-spark-application-with-udfs-on-yarn-which-environment-variables-and-parameters-should-i-use"></a>Ricerca per categorie eseguire l'applicazione Spark con funzioni definite dall'utente in YARN? Quali variabili e parametri di ambiente è opportuno usare?

**Risposta:** Per avviare l'applicazione Spark in YARN, è necessario specificare le variabili di ambiente come `spark.yarn.appMasterEnv.[EnvironmentVariableName]`. Vedere di seguito come esempio di utilizzo di `spark-submit`:

```powershell
spark-submit \
--class org.apache.spark.deploy.dotnet.DotnetRunner \
--master yarn \
--deploy-mode cluster \
--conf spark.yarn.appMasterEnv.DOTNET_WORKER_DIR=./worker/Microsoft.Spark.Worker-<version> \
--conf spark.yarn.appMasterEnv.DOTNET_ASSEMBLY_SEARCH_PATHS=./udfs \
--archives hdfs://<path to your files>/Microsoft.Spark.Worker.net461.win-x64-<version>.zip#worker,hdfs://<path to your files>/mySparkApp.zip#udfs \
hdfs://<path to jar file>/microsoft-spark-2.4.x-<version>.jar \
hdfs://<path to your files>/mySparkApp.zip mySparkApp
```

## <a name="next-steps"></a>Passaggi successivi

* [Introduzione a .NET per Apache Spark](../tutorials/get-started.md)
* [Eseguire il debug di un'applicazione .NET per Apache Spark in Windows](../how-to-guides/debug.md)
