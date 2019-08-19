---
title: Introduzione a .NET per Apache Spark
description: Scopri come eseguire un'app .NET per Apache Spark usando .NET Core in Windows.
ms.date: 06/27/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 7ce7d7aec6c15385d3d797d5a548519eea33b764
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "69577008"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a>Esercitazione: Introduzione a .NET per Apache Spark

Questa esercitazione illustra come eseguire un'app .NET per Apache Spark usando .NET Core in Windows.

In questa esercitazione si imparerà a:

> [!div class="checklist"]
> * Preparare l'ambiente Windows per .NET per Apache Spark
> * Scaricare **Microsoft. Spark. Worker**
> * Creazione ed esecuzione di un'applicazione .NET semplice per Apache Spark

## <a name="prepare-your-environment"></a>Preparare l'ambiente

Prima di iniziare, verificare che sia possibile eseguire `dotnet` `mvn`, `java`,, `spark-shell` dalla riga di comando. Se l'ambiente è già preparato, è possibile passare alla sezione successiva. Se non è possibile eseguire uno o tutti i comandi, attenersi alla procedura riportata di seguito.

1. Scaricare e installare [.NET Core 2.1 x SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1). L'installazione dell'SDK consente `dotnet` di aggiungere gli attrezzi per il percorso. Usare il comando `dotnet --version` di PowerShell per verificare l'installazione.

2. Installare [Visual studio 2017](https://www.visualstudio.com/downloads/) o [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) con gli aggiornamenti più recenti. È possibile usare community, Professional o Enterprise. La versione community è gratuita.

   Scegliere i carichi di lavoro seguenti durante l'installazione:
      * Sviluppo per desktop .NET
          * Tutti i componenti necessari
          * Strumenti di sviluppo per .NET Framework 4.6.1
      * Sviluppo multipiattaforma .NET Core
          * Tutti i componenti necessari

3. Installare [Java 1,8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).

    * Selezionare la versione appropriata per il sistema operativo in uso. Ad esempio, selezionare **JDK-8u201-Windows-x64. exe** per un computer Windows x64.
    * Usare il comando `java -version` di PowerShell per verificare l'installazione.

4. Installare [Apache Maven 3.6.0 +](https://maven.apache.org/download.cgi).
    * Scaricare [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip).
    * Estrarre in una directory locale. Ad esempio `c:\bin\apache-maven-3.6.0\`.
    * Aggiungere Apache Maven alla [variabile di ambiente Path](https://www.java.com/en/download/help/path.xml). Se è stato estratto `c:\bin\apache-maven-3.6.0\`in, si aggiungerà `c:\bin\apache-maven-3.6.0\bin` al percorso.
    * Usare il comando `mvn -version` di PowerShell per verificare l'installazione.

5. Installare [Apache Spark 2.3 +](https://spark.apache.org/downloads.html). Apache Spark 2.4 + non è supportato.
    * Scaricare [Apache Spark 2.3 +](https://spark.apache.org/downloads.html) ed estrarlo in una cartella locale usando uno strumento come [7-zip](https://www.7-zip.org/) o [WinZip](https://www.winzip.com/). Ad esempio, è possibile estrarlo in `c:\bin\spark-2.3.2-bin-hadoop2.7\`.
    * Aggiungere Apache Spark alla [variabile di ambiente Path](https://www.java.com/en/download/help/path.xml). Se è stato estratto `c:\bin\spark-2.3.2-bin-hadoop2.7\`in, si aggiungerà `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` al percorso.
    * Aggiungere una [nuova variabile](https://www.java.com/en/download/help/path.xml) di ambiente `SPARK_HOME`denominata. Se è stato estratto `C:\bin\spark-2.3.2-bin-hadoop2.7\`in, `C:\bin\spark-2.3.2-bin-hadoop2.7\` utilizzare per il **valore della variabile**.
    * Verificare che sia possibile eseguire `spark-shell` dalla riga di comando.

6. Configurare [file winutils](https://github.com/steveloughran/winutils).
    * Scaricare il file binario **file winutils. exe** dal [repository file winutils](https://github.com/steveloughran/winutils). Consente di selezionare la versione di Hadoop con la quale è stata compilata la distribuzione Spark. Ad esempio, si usa **Hadoop-2.7.1** per **Spark 2.3.2**. La versione di Hadoop viene annotata alla fine del nome della cartella di installazione di Spark.
    * Salvare il file binario **file winutils. exe** in una directory di propria scelta. Ad esempio `c:\hadoop\bin`.
    * Impostare `HADOOP_HOME` per riflettere la directory con **file winutils. exe** senza `bin`. Ad esempio `c:\hadoop`.
    * Impostare la variabile di ambiente PATH da `%HADOOP_HOME%\bin`includere.

Verificare che sia possibile `dotnet`eseguire, `java`, `mvn`, `spark-shell` dalla riga di comando prima di passare alla sezione successiva.

## <a name="download-the-microsoftsparkworker-release"></a>Scaricare la versione Microsoft. Spark. Worker

1. Scaricare la versione [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) dalla pagina .net per Apache Spark le versioni di GitHub nel computer locale. Ad esempio, è possibile scaricarlo nel percorso `c:\bin\Microsoft.Spark.Worker\`.

2. Creare una [nuova variabile](https://www.java.com/en/download/help/path.xml) di ambiente `DotnetWorkerPath` denominata e impostarla sulla directory in cui è stato scaricato ed estratto **Microsoft. Spark. Worker**. Ad esempio `c:\bin\Microsoft.Spark.Worker`.

## <a name="clone-the-net-for-apache-spark-github-repo"></a>Clonare .NET per Apache Spark repository GitHub

Usare il comando [GitBash](https://gitforwindows.org/) seguente per clonare .net per Apache Spark repository nel computer.

```bash
git clone https://github.com/dotnet/spark.git c:\github\dotnet-spark
```

## <a name="write-a-net-for-apache-spark-app"></a>Scrivere un'app .NET per Apache Spark

1. Aprire **Visual Studio** e passare a **file > creare un nuovo progetto > app console (.NET Core)** . Denominare l'applicazione **HelloSpark**.

2. Installare il [pacchetto NuGet Microsoft. Spark](https://www.nuget.org/profiles/spark). Per altre informazioni sull'installazione di pacchetti NuGet, vedere [diversi modi per installare un pacchetto NuGet](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package).

3. In **Esplora soluzioni**aprire **Program.cs** e scrivere il codice seguente C# :

   ```csharp
     var spark = SparkSession.Builder().GetOrCreate();
     var df = spark.Read().Json("people.json");
     df.Show();
   ```

4. Compilare la soluzione.

## <a name="run-your-net-for-apache-spark-app"></a>Eseguire .NET per Apache Spark app

1. Aprire **PowerShell** e sostituire la directory con la cartella in cui è archiviata l'app.

   ```powershell
   cd <your-app-output-directory>
   ```

2. Creare un file denominato **people. JSON** con il contenuto seguente:

   ```json
   {"name":"Michael"}
   {"name":"Andy", "age":30}
   {"name":"Justin", "age":19}
   ```

3. Usare il comando di PowerShell seguente per eseguire l'app:

   ```powershell
    spark-submit `
    --class org.apache.spark.deploy.dotnet.DotnetRunner `
    --master local `
    microsoft-spark-2.4.x-<version>.jar `
    dotnet HelloSpark.dll
    ```

La procedura è stata completata. La creazione e l'esecuzione di .NET per Apache Spark app sono state completate.

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione si è appreso come:
> [!div class="checklist"]
> * Preparare l'ambiente Windows per .NET per Apache Spark
> * Scaricare **Microsoft. Spark. Worker**
> * Creazione ed esecuzione di un'applicazione .NET semplice per Apache Spark

Per altre informazioni, vedere la pagina delle risorse.
> [!div class="nextstepaction"]
> [.NET per risorse Apache Spark](../resources/index.md)
