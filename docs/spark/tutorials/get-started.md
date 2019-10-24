---
title: Introduzione a .NET per Apache Spark
description: Informazioni su come eseguire un'app .NET per Apache Spark usando .NET Core in Windows.
ms.date: 06/27/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 19efc8412d834d73069c61e1cc1ccd9e5eb8593b
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774367"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a>Esercitazione: Introduzione a .NET per Apache Spark

Questa esercitazione illustra come eseguire un'app .NET per Apache Spark con .NET Core in Windows.

In questa esercitazione si imparerà a:

> [!div class="checklist"]
>
> * Preparare l'ambiente Windows per .NET per Apache Spark
> * Scaricare **Microsoft.Spark.Worker**
> * Creare ed eseguire un'applicazione .NET per Apache Spark semplice

## <a name="prepare-your-environment"></a>Preparare l'ambiente

Prima di iniziare, verificare che sia possibile eseguire `dotnet`, `java`, `mvn`, `spark-shell` dalla riga di comando. Se l'ambiente è già preparato, è possibile passare alla sezione successiva. Se non è possibile eseguire uno o tutti i comandi, seguire questa procedura.

1. Scaricare e installare [.NET Core 2.1x SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1). L'installazione dell'SDK consente di aggiungere la toolchain `dotnet` a PATH. Usare il comando `dotnet --version` di PowerShell per verificare l'installazione.

2. Installare [Visual Studio 2017](https://www.visualstudio.com/downloads/) o [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) con gli aggiornamenti più recenti. È possibile usare l'edizione Community, Professional o Enterprise. La versione Community è gratuita.

   Scegliere i carichi di lavoro seguenti durante l'installazione:
      * Sviluppo per desktop .NET
          * Tutti i componenti richiesti
          * Strumenti di sviluppo per .NET Framework 4.6.1
      * Sviluppo multipiattaforma .NET Core
          * Tutti i componenti richiesti

3. Installare [Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).

    * Selezionare la versione appropriata per il sistema operativo in uso. Ad esempio, selezionare **jdk-8u201-windows-x64.exe** per un computer Windows x64.
    * Usare il comando `java -version` di PowerShell per verificare l'installazione.

4. Installare [Apache Maven 3.6.0+](https://maven.apache.org/download.cgi).
    * Scaricare [Apache Maven 3.6.2](http://mirror.metrocast.net/apache/maven/maven-3/3.6.2/binaries/apache-maven-3.6.2-bin.zip).
    * Estrarre i file in una directory locale. Ad esempio `c:\bin\apache-maven-3.6.2\`.
    * Aggiungere Apache Maven alla [variabile di ambiente PATH](https://www.java.com/en/download/help/path.xml). Se i file vengono estratti in `c:\bin\apache-maven-3.6.2\`, aggiungere `c:\bin\apache-maven-3.6.2\bin` a PATH.
    * Usare il comando `mvn -version` di PowerShell per verificare l'installazione.

5. Installare [Apache Spark 2.3+](https://spark.apache.org/downloads.html). Apache Spark 2.4+ non è supportato.
    * Scaricare [Apache Spark 2.3+](https://spark.apache.org/downloads.html) ed estrarre i file in una cartella locale usando uno strumento come [7-zip](https://www.7-zip.org/) o [WinZip](https://www.winzip.com/). Ad esempio, è possibile estrarre i file in `c:\bin\spark-2.3.2-bin-hadoop2.7\`.
    * Aggiungere Apache Spark alla [variabile di ambiente PATH](https://www.java.com/en/download/help/path.xml). Se i file vengono estratti in `c:\bin\spark-2.3.2-bin-hadoop2.7\`, aggiungere `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` a PATH.
    * Aggiungere una [nuova variabile di ambiente](https://www.java.com/en/download/help/path.xml) denominata `SPARK_HOME`. Se i file sono stati estratti in `C:\bin\spark-2.3.2-bin-hadoop2.7\`, usare `C:\bin\spark-2.3.2-bin-hadoop2.7\` per **Valore della variabile**.
    * Verificare che sia possibile eseguire `spark-shell` dalla riga di comando.

6. Installare [WinUtils](https://github.com/steveloughran/winutils).
    * Scaricare il file binario **winutils.exe** dal [repository WinUtils](https://github.com/steveloughran/winutils). Selezionare la versione di Hadoop con la quale è stata compilata la distribuzione Spark. Ad esempio, si usa **hadoop-2.7.1** per **Spark 2.3.2**. La versione di Hadoop viene indicata alla fine del nome della cartella di installazione di Spark.
    * Salvare il file binario **winutils.exe** in una directory a propria scelta. Ad esempio `c:\hadoop\bin`.
    * Impostare `HADOOP_HOME` in modo che rispecchi la directory con **winutils.exe** senza `bin`. Ad esempio `c:\hadoop`.
    * Impostare la variabile di ambiente PATH per includere `%HADOOP_HOME%\bin`.

Verificare che sia possibile eseguire `dotnet`, `java`, `mvn`, `spark-shell` dalla riga di comando prima di passare alla sezione successiva.

## <a name="download-the-microsoftsparkworker-release"></a>Scaricare Microsoft.Spark.Worker

1. Scaricare [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) dalla pagina di GitHub dei rilasci per .NET per Apache Spark nel computer locale. Ad esempio, è possibile scaricarlo nel percorso `c:\bin\Microsoft.Spark.Worker\`.

2. Creare una [nuova variabile di ambiente](https://www.java.com/en/download/help/path.xml) denominata `DOTNET_WORKER_DIR` e impostarla sulla directory in cui è stato scaricato ed estratto **Microsoft.Spark.Worker**. Ad esempio `c:\bin\Microsoft.Spark.Worker`.

## <a name="clone-the-net-for-apache-spark-github-repo"></a>Clonare il repository GitHub di .NET per Apache Spark

Usare il comando [GitBash](https://gitforwindows.org/) seguente per clonare il repository di .NET per Apache Spark nel computer.

```bash
git clone https://github.com/dotnet/spark.git c:\github\dotnet-spark
```

## <a name="write-a-net-for-apache-spark-app"></a>Scrivere un'app .NET per Apache Spark

1. Aprire **Visual Studio** e passare a **File > Crea nuovo progetto > App console (.NET Core**). Denominare l'applicazione **HelloSpark**.

2. Installare il [pacchetto NuGet Microsoft.Spark](https://www.nuget.org/profiles/spark). Per altre informazioni sull'installazione di pacchetti NuGet, vedere [Diversi modi per installare un pacchetto NuGet](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package).

3. In **Esplora soluzioni** aprire **Program.cs** e scrivere il codice C# seguente:

   ```csharp
     var spark = SparkSession.Builder().GetOrCreate();
     var df = spark.Read().Json("people.json");
     df.Show();
   ```

4. Compilare la soluzione.

## <a name="run-your-net-for-apache-spark-app"></a>Eseguire l'app .NET per Apache Spark

1. Aprire **PowerShell** e impostare la directory sulla cartella in cui è archiviata l'app.

   ```powershell
   cd <your-app-output-directory>
   ```

2. Creare un file denominato **people.json** con il contenuto seguente:

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

La procedura è stata completata. È stata creata ed eseguita un'app .NET per Apache Spark.

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione si è appreso come:
> [!div class="checklist"]
>
> * Preparare l'ambiente Windows per .NET per Apache Spark
> * Scaricare **Microsoft.Spark.Worker**
> * Creare ed eseguire un'applicazione .NET per Apache Spark semplice

Per altre informazioni, vedere la pagina delle risorse.
> [!div class="nextstepaction"]
> [Risorse di .NET per Apache Spark](../resources/index.md)
