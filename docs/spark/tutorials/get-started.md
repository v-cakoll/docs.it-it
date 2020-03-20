---
title: Introduzione a .NET per Apache Spark
description: Scopri come eseguire un'app .NET per Apache Spark usando .NET Core in Windows, MacOS e Ubuntu.
ms.date: 01/31/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 7375c385245a05d7dc29d5df89d875bf6cb4141a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79187547"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a>Esercitazione: Introduzione a .NET per Apache SparkTutorial: Get started with .NET for Apache Spark

Questa esercitazione illustra come eseguire un'app .NET per Apache Spark usando .NET Core in Windows, MacOS e Ubuntu.

In questa esercitazione verranno illustrate le procedure per:

> [!div class="checklist"]
>
> * Preparare l'ambiente per .NET per Apache Spark
> * Scrivere la prima applicazione .NET per Apache Spark
> * Compilare ed eseguire la semplice applicazione .NET per Apache Spark

## <a name="prepare-your-environment"></a>Preparare l'ambiente

Prima di iniziare a scrivere l'app, è necessario configurare alcune dipendenze dei prerequisiti. Se è `dotnet`possibile `java` `mvn`eseguire `spark-shell` , , , dall'ambiente della riga di comando, l'ambiente è già pronto ed è possibile passare alla sezione successiva. Se non è possibile eseguire uno o tutti i comandi, eseguire la procedura seguente.

### <a name="1-install-net"></a>1. Installare .NET

Per iniziare a creare app .NET, è necessario scaricare e installare .NET SDK (Software Development Kit).

Scaricare e installare [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1). L'installazione dell'SDK consente di aggiungere la toolchain `dotnet` a PATH.

Dopo aver installato .NET Core SDK, aprire un nuovo `dotnet`prompt dei comandi o un nuovo terminale ed eseguire .

Se il comando viene eseguito e stampa informazioni su come utilizzare dotnet, è possibile passare al passaggio successivo. Se viene `'dotnet' is not recognized as an internal or external command` visualizzato un errore, assicurarsi di aver aperto un nuovo prompt dei comandi o un **nuovo** terminale prima di eseguire il comando.

### <a name="2-install-java"></a>2. Installare Java

Installare [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) per Windows e MacOS o [OpenJDK 8](https://openjdk.java.net/install/) per Ubuntu.

Selezionare la versione appropriata per il sistema operativo in uso. Ad esempio, selezionare **jdk-8u201-windows-x64.exe** per un computer Windows x64 (come illustrato di seguito) o **jdk-8u231-macosx-x64.dmg** per MacOS. Quindi, utilizzare `java` il comando per verificare l'installazione.

![Java Scarica](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-compression-software"></a>3. Installare il software di compressione

Apache Spark viene scaricato come file .tgz compresso. Per estrarre il file, utilizzare un programma di estrazione, ad esempio [7](https://www.7-zip.org/) zip o [Win.ip.](https://www.winzip.com/)

### <a name="4-install-apache-spark"></a>4. Installare Apache Spark

[Scaricare e installare Apache Spark](https://spark.apache.org/downloads.html). È necessario scegliere tra la versione 2.3.o o 2.4.0, 2.4.1, 2.4.3 o 2.4.4 (.NET per Apache Spark non è compatibile con altre versioni di Apache Spark).

I comandi utilizzati nei passaggi seguenti presuppongono che sia stato [scaricato e installato Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz). Se si desidera utilizzare una versione diversa, sostituire **2.4.1** con il numero di versione appropriato. Quindi, estrarre il file **.tar** e i file Apache Spark.

Per estrarre il file **.tar** nidificato:

* Individuare il file **spark-2.4.1-bin-hadoop2.7.tgz** scaricato.
* Fare clic con il pulsante destro del mouse sul file e selezionare **7-zip -> Estrai qui**.
* **spark-2.4.1-bin-hadoop2.7.tar** viene creato insieme al file **.tgz** scaricato.

Per estrarre i file Apache Spark:

* Fare clic con il pulsante destro del mouse su **spark-2.4.1-bin-hadoop2.7.tar** e selezionare **7-zip -> Estrarre i file...**
* Nel campo **Estrai** in, estrai **C:**
* Deselezionare la casella di controllo sotto il campo **Estrai in.**
* Selezionare **OK**.
* I file di Apache Spark vengono estratti in C:

![Installare Spark](https://dotnet.microsoft.com/static/images/spark-extract-with-7-zip.png?v=YvjUv54LIxI9FbALPC3h8zSQdyMtK2-NKbFOliG-f8M)

Eseguire i comandi seguenti per impostare le variabili di ambiente utilizzate per individuare Apache Spark in **Windows:**

```console
setx HADOOP_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
setx SPARK_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
```

Eseguire i comandi seguenti per impostare le variabili di ambiente utilizzate per individuare Apache Spark su **MacOS** e **Ubuntu**:

```bash
export SPARK_HOME=~/bin/spark-2.4.1-bin-hadoop2.7/
export PATH="$SPARK_HOME/bin:$PATH"
source ~/.bashrc
```

Dopo aver installato tutto e impostato le variabili di ambiente, aprire un nuovo prompt dei comandi o un **nuovo** terminale ed eseguire il comando seguente:

`%SPARK_HOME%\bin\spark-submit --version`

Se il comando viene eseguito e stampa le informazioni sulla versione, è possibile passare al passaggio successivo.

Se viene `'spark-submit' is not recognized as an internal or external command` visualizzato un errore, assicurarsi di aver aperto un **nuovo** prompt dei comandi.

### <a name="5-install-net-for-apache-spark"></a>5. Installare .NET per Apache Spark

Scaricare la versione Microsoft.Spark.Worker da .NET per Apache Spark GitHub.Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub. Ad esempio, se si utilizza un computer Windows e si prevede di utilizzare .NET Core, [scaricare la versione x64 netcoreapp3.1 di Windows.](https://github.com/dotnet/spark/releases/download/v0.8.0/Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip)

Per estrarre Microsoft.Spark.Worker:

* Individuare il file **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip** scaricato.
* Fare clic con il pulsante destro del mouse e selezionare **7-zip -> Estrai file...**.
* Nel campo **Estrai** in, estrai **C:**
* Deselezionare la casella di controllo sotto il campo **Estrai in.**
* Selezionare **OK**.

![Installare .NET Spark](https://dotnet.microsoft.com/static/images/dotnet-for-spark-extract-with-7-zip.png?v=jwCyum9mL0mGIi4V5zC7yuvLfcj1_nL-QFFD8TClhZk)

### <a name="6-install-winutils-windows-only"></a>6. Installare WinUtils (solo Windows)

.NET per Apache Spark richiede l'installazione di WinUtils insieme a Apache Spark. [Scaricare winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe). Quindi, copiare WinUtils in **C:**

> [!NOTE]
> Se si utilizza una versione diversa di Hadoop, annotata alla fine del nome della cartella di installazione di Spark, [selezionare la versione di WinUtils](https://github.com/steveloughran/winutils) compatibile con la versione di Hadoop in uso.

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a>7. Impostare DOTNET_WORKER_DIR e controllare le dipendenze

Eseguire uno dei comandi seguenti `DOTNET_WORKER_DIR` per impostare la variabile di ambiente, che viene utilizzata dalle app .NET per individuare .NET per Apache Spark.

In **Windows**creare una [nuova variabile](https://www.java.com/en/download/help/path.xml) `DOTNET_WORKER_DIR` di ambiente e impostarla sulla directory in cui è `C:\bin\Microsoft.Spark.Worker\`stato scaricato ed estrarre Microsoft.Spark.Worker, ad esempio .

In **MacOS**, creare una `export DOTNET_WORKER_DIR <your_path>` nuova variabile di ambiente utilizzando e impostarla sulla directory in cui è stato scaricato ed estratto microsoft.Spark.Worker (ad esempio, */bin/Microsoft.Spark.Worker/*).

In **Ubuntu**, creare una [nuova variabile](https://help.ubuntu.com/community/EnvironmentVariables) `DOTNET_WORKER_DIR` di ambiente e impostarla sulla directory in cui è stato scaricato ed estratto Microsoft.Spark.Worker (ad esempio, */bin/Microsoft.Spark.Worker*).

Infine, verificare che sia `dotnet` `java`possibile `mvn` `spark-shell` eseguire , , , dalla riga di comando prima di passare alla sezione successiva.

## <a name="write-a-net-for-apache-spark-app"></a>Scrivere un'app .NET per Apache Spark

### <a name="1-create-a-console-app"></a>1. Creare un'app console

Nel prompt dei comandi o nel terminale, eseguire i comandi seguenti per creare una nuova applicazione console:

```dotnetcli
dotnet new console -o mySparkApp
cd mySparkApp
```

Il `dotnet` comando `new` crea automaticamente `console` un'applicazione di tipo. Il `-o` parametro crea una directory denominata *mySparkApp* in cui è archiviata l'app e la popola con i file necessari. Il `cd mySparkApp` comando modifica la directory in base alla directory dell'app appena creata.

### <a name="2-install-nuget-package"></a>2. Installare il pacchetto NuGet

Per usare .NET per Apache Spark in un'app, installa il pacchetto Microsoft.Spark. Nel prompt dei comandi o nel terminale, eseguire il comando seguente:

`dotnet add package Microsoft.Spark --version 0.8.0`

### <a name="3-code-your-app"></a>3. Codifica la tua app

Aprire *Program.cs* in Visual Studio Code o in qualsiasi editor di testo e sostituire tutto il codice con quanto segue:

```csharp
using Microsoft.Spark.Sql;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a Spark session.
            SparkSession spark = SparkSession
                .Builder()
                .AppName("word_count_sample")
                .GetOrCreate();

            // Create initial DataFrame.
            DataFrame dataFrame = spark.Read().Text("input.txt");

            // Count words.
            DataFrame words = dataFrame
                .Select(Functions.Split(Functions.Col("value"), " ").Alias("words"))
                .Select(Functions.Explode(Functions.Col("words"))
                .Alias("word"))
                .GroupBy("word")
                .Count()
                .OrderBy(Functions.Col("count").Desc());

            // Show results.
            words.Show();

            // Stop Spark session.
            spark.Stop();
        }
    }
}
```

### <a name="4-create-and-add-a-data-file"></a>4. Creare e aggiungere un file di dati

Apri il prompt dei comandi o il terminale e accedi alla cartella dell'app.

```bash
cd <your-app-output-directory>
```

L'app elabora un file contenente righe di testo. Creare un file *input.txt* nella directory *mySparkApp,* contenente il seguente testo:

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

## <a name="run-your-net-for-apache-spark-app"></a>Eseguire l'app .NET per Apache Spark

1. Eseguire il comando seguente per compilare l'applicazione:

   ```dotnetcli
   dotnet build
   ```

2. Eseguire il comando seguente per inviare l'applicazione per l'esecuzione su Apache Spark:

   ```console
   spark-submit \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --master local \
   microsoft-spark-2.4.x-<version>.jar \
   dotnet HelloSpark.dll
   ```

   > [!NOTE]
   > Questo comando presuppone che sia stato scaricato Apache Spark e che `spark-submit`sia stato aggiunto alla variabile di ambiente PATH per poter utilizzare . In caso contrario, è necessario utilizzare il percorso completo (ad esempio, *C:* *~/spark/bin/spark-submit*

3. Quando l'app viene eseguita, i dati del conteggio delle parole del file *input.txt* vengono scritti nella console.

Congratulazioni! È stata creata ed eseguita un'app .NET per Apache Spark.

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione sono state illustrate le procedure per:
> [!div class="checklist"]
>
> * Preparare l'ambiente Windows per .NET per Apache Spark
> * Scrivere la prima applicazione .NET per Apache Spark
> * Compilare ed eseguire la semplice applicazione .NET per Apache Spark

Per un video che illustra i passaggi precedenti, estrarre la [serie di video .NET per Apache Spark 101.](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App)

Per altre informazioni, vedere la pagina delle risorse.
> [!div class="nextstepaction"]
> [Risorse di .NET per Apache Spark](../resources/index.md)
