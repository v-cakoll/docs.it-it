---
title: Distribuire .NET per Apache Spark worker e file binari di funzioni definite dall'utenteDeploy .NET for Apache Spark worker and user-defined function binaries
description: Informazioni su come distribuire .NET per il lavoro Apache Spark e i file binari delle funzioni definite dall'utente.
ms.date: 01/21/2019
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: f373ccee398149adcadeac91f02d9896214706b0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79187600"
---
# <a name="deploy-net-for-apache-spark-worker-and-user-defined-function-binaries"></a>Distribuire .NET per Apache Spark worker e file binari di funzioni definite dall'utenteDeploy .NET for Apache Spark worker and user-defined function binaries

In questa procedura vengono fornite istruzioni generali su come distribuire .NET per il worker Apache Spark e i file binari delle funzioni definite dall'utente. Si apprendono quali variabili di ambiente impostare, nonché `spark-submit`alcuni parametri di uso comune per l'avvio di applicazioni con .

## <a name="configurations"></a>Configurazioni
Le configurazioni mostrano le impostazioni generali delle variabili di ambiente e dei parametri per distribuire .NET per Apache Spark worker e binari di funzioni definite dall'utente.

### <a name="environment-variables"></a>Variabili di ambiente
Quando si distribuiscono i worker e si scrivono funzioni definite dall'utente, è possibile impostare alcune variabili di ambiente di uso comune:When deploying workers and writing UDFs, there are a few commonly used environment variables that you may need to set:

| Variabile di ambiente         | Descrizione
| :--------------------------- | :----------
| DOTNET_WORKER_DIR            | Percorso in <code>Microsoft.Spark.Worker</code> cui è stato generato il file binario.</br>Viene utilizzato dal driver Spark e verrà passato agli esecutori Spark. Se questa variabile non è impostata, gli esecutori <code>PATH</code> Spark cercheranno il percorso specificato nella variabile di ambiente.</br>_ad esempio, "C:"bin"Microsoft.Spark.Worker"_
| DOTNET_ASSEMBLY_SEARCH_PATHS | Percorsi delimitati <code>Microsoft.Spark.Worker</code> da virgole in cui verranno caricati gli assembly.</br>Si noti che se un percorso inizia con ".", verrà antedata la directory di lavoro. Se in **modalità filato**, "." rappresenterebbe la directory di lavoro del contenitore.</br>_ad\\&lt;esempio" nome utente&gt;\\&lt;Mysparkapp&gt;\\&lt;: nome&gt;utente "_
| DOTNET_WORKER_DEBUG          | Se si desidera eseguire il debug di una <code>1</code> funzione <code>spark-submit</code> <a href="https://github.com/dotnet/spark/blob/master/docs/developer-guide.md#debugging-user-defined-function-udf">definita dall'utente</a>, impostare questa variabile di ambiente su prima dell'esecuzione di .

### <a name="parameter-options"></a>Opzioni dei parametri:
Una volta che l'applicazione Spark è `spark-submit` [in bundle,](https://spark.apache.org/docs/latest/submitting-applications.html#bundling-your-applications-dependencies)è possibile avviarla utilizzando . La tabella seguente mostra alcune delle opzioni comunemente utilizzate:

| Nome parametro        | Descrizione
| :---------------------| :----------
| --class               | Punto di ingresso per l'applicazione.</br>_e.g. org.apache.spark.deploy.dotnet.DotnetRunner_
| --master              | <a href="https://spark.apache.org/docs/latest/submitting-applications.html#master-urls">URL master</a> per il cluster.</br>_ad esempio filato_
| --deploy-mode (modalità di distribuzione)         | Se distribuire il driver nei<code>cluster</code>nodi di lavoro (<code>client</code>) o localmente come client esterno ( ).</br>Valore predefinito: <code>client</code>
| --conf                | Proprietà di configurazione Spark arbitraria in <code>key=value</code> formato.</br>_ad esempio spark.yarn.appMasterEnv.DOTNET_WORKER_DIR . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . ._
| --files (file)               | Elenco separato da virgole dei file da inserire nella directory di lavoro di ogni esecutore.<br/><ul><li>Si prega di notare che questa opzione è applicabile solo per la modalità filato.</li><li>Supporta la specifica di nomi di file con il simbolo , simile a Hadoop.</br></ul>_ad esempio <code>myLocalSparkApp.dll#appSeen.dll</code>. L'applicazione deve usare <code>appSeen.dll</code> il <code>myLocalSparkApp.dll</code> nome come riferimento durante l'esecuzione su YARN._</li>
| --archivi          | Elenco delimitato da virgole di archivi da estrarre nella directory di lavoro di ogni esecutore.</br><ul><li>Si prega di notare che questa opzione è applicabile solo per la modalità filato.</li><li>Supporta la specifica di nomi di file con il simbolo , simile a Hadoop.</br></ul>_ad esempio <code>hdfs://&lt;path to your worker file&gt;/Microsoft.Spark.Worker.zip#worker</code>. Questo copierà ed estrarrà il file zip <code>worker</code> nella cartella._</li>
| application-jar       | Percorso di un jar in bundle che include l'applicazione e tutte le dipendenze.</br>_ad esempio hdfs://&lt;percorso al&gt;tuo jar /microsoft-spark-&lt;versione&gt;.jar_
| application-arguments | Argomenti passati al metodo principale della classe principale, se presente.</br>_ad esempio,&lt;hdfs:// percorso&gt;/&lt;&gt;dell'app, &lt;il&gt; &lt;file zip dell'app è args dell'app&gt;_

> [!NOTE]
> Specificare `--options` tutto `application-jar` il prima `spark-submit`all'avvio di applicazioni con , altrimenti verranno ignorate. Per ulteriori informazioni, vedere [ `spark-submit` opzioni](https://spark.apache.org/docs/latest/submitting-applications.html) ed esecuzione di [spark sui dettagli di YARN](https://spark.apache.org/docs/latest/running-on-yarn.html).

## <a name="frequently-asked-questions"></a>Domande frequenti
### <a name="when-i-run-a-spark-app-with-udfs-i-get-a-filenotfoundexception-error-what-should-i-do"></a>Quando si esegue un'app spark con funzioni definite dall'utente, viene visualizzato un errore 'FileNotFoundException'. Cosa devo fare?
> **Errore:** [Errore] [TaskRunner] [0] ProcessStream() non riuscito con eccezione: System.IO.FileNotFoundException: assembly 'mySparkApp, Version '1.0.0.0, Culture 'neutral, PublicKeyToken' file non trovato: 'mySparkApp.dll'

**Risposta:** Verificare `DOTNET_ASSEMBLY_SEARCH_PATHS` che la variabile di ambiente sia impostata correttamente. Deve essere il percorso `mySparkApp.dll`che contiene il file .

### <a name="after-i-upgraded-my-net-for-apache-spark-version-and-reset-the-dotnet_worker_dir-environment-variable-why-do-i-still-get-the-following-ioexception-error"></a>Dopo aver aggiornato il mio .NET per la `DOTNET_WORKER_DIR` versione Apache Spark e `IOException` reimpostare la variabile di ambiente, perché è ancora possibile ottenere il seguente errore?
> **Errore:** Attività persa 0.0 nella fase 11.0 (TID 24, localhost, driver esecutore): java.io.IOException: Impossibile eseguire il programma "Microsoft.Spark.Worker.exe": errore CreateProcess 2, Il sistema non riesce a trovare il file specificato.

**Risposta:** Provare a riavviare prima la finestra di PowerShell (o altre finestre di comando) in modo che possa accettare i valori delle variabili di ambiente più recenti. Quindi avviare il programma.

### <a name="after-submitting-my-spark-application-i-get-the-error-systemtypeloadexception-could-not-load-type-systemruntimeremotingcontextscontext"></a>Dopo aver inviato la mia applicazione `System.TypeLoadException: Could not load type 'System.Runtime.Remoting.Contexts.Context'`Spark, ricevo l'errore .
> **Errore:** [Errore] [TaskRunner] [0] ProcessStream() non riuscito con l'eccezione: System.TypeLoadException: Impossibile caricare il tipo 'System.Runtime.Remoting.Contexts.Context' dall'assembly 'mscorlib, Version'4.0.0.0, Culture 'neutral, PublicKeyToken'...'.

**Risposta:** Controllare `Microsoft.Spark.Worker` la versione in uso. Esistono due versioni: **.NET Framework 4.6.1** e **.NET Core 2.1.x**. In questo `Microsoft.Spark.Worker.net461.win-x64-<version>` caso, (che è possibile `System.Runtime.Remoting.Contexts.Context` [scaricare](https://github.com/dotnet/spark/releases)) deve essere utilizzato poiché è solo per .NET Framework.

### <a name="how-do-i-run-my-spark-application-with-udfs-on-yarn-which-environment-variables-and-parameters-should-i-use"></a>Come si esegue l'applicazione spark con UDF su YARN? Quali variabili di ambiente e parametri è necessario utilizzare?

**Risposta:** Per avviare l'applicazione spark su YARN, `spark.yarn.appMasterEnv.[EnvironmentVariableName]`le variabili di ambiente devono essere specificate come . Si prega di vedere `spark-submit`di seguito come esempio utilizzando :

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
