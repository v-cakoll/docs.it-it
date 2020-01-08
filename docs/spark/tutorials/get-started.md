---
title: Introduzione a .NET per Apache Spark
description: Informazioni su come eseguire un'app .NET per Apache Spark usando .NET Core in Windows.
ms.date: 11/04/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 934b91a258937a976804109c71df232b8ce6d6d7
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337596"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a>Esercitazione: Introduzione a .NET per Apache Spark

Questa esercitazione illustra come eseguire un'app .NET per Apache Spark con .NET Core in Windows.

In questa esercitazione si imparerà a:

> [!div class="checklist"]
>
> * Preparare l'ambiente Windows per .NET per Apache Spark
> * Scrivere la prima applicazione .NET per Apache Spark
> * Creazione ed esecuzione di un'applicazione .NET semplice per Apache Spark

## <a name="prepare-your-environment"></a>Preparazione dell'ambiente

Prima di iniziare a scrivere l'app, è necessario configurare alcune dipendenze dei prerequisiti. Se è possibile eseguire `dotnet`, `java`, `mvn``spark-shell` dall'ambiente della riga di comando, l'ambiente è già pronto ed è possibile passare alla sezione successiva. Se non è possibile eseguire uno o tutti i comandi, seguire questa procedura.

### <a name="1-install-net"></a>1. installare .NET

Per iniziare a creare app .NET, è necessario scaricare e installare .NET SDK (Software Development Kit).

scaricare e installare [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.0). L'installazione dell'SDK consente di aggiungere la toolchain `dotnet` a PATH.

Una volta installato il .NET Core SDK, aprire un nuovo prompt dei comandi ed eseguire `dotnet`.

Se il comando viene eseguito e stampa le informazioni su come usare dotnet, può passare al passaggio successivo. Se viene visualizzato un errore di `'dotnet' is not recognized as an internal or external command`, assicurarsi di aprire un **nuovo** prompt dei comandi prima di eseguire il comando.

### <a name="2-install-java"></a>2. installare Java

Installare [Java 8,1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).

Selezionare la versione appropriata per il sistema operativo in uso. Ad esempio, selezionare **jdk-8u201-windows-x64.exe** per un computer Windows x64. Usare quindi il comando `java` per verificare l'installazione.

![Download Java](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-7-zip"></a>3. installare 7-zip

Apache Spark viene scaricato come file con estensione TGZ compresso. Per estrarre il file, usare un programma di estrazione, ad esempio 7-zip.

* Visita [7-download zip](https://www.7-zip.org/).
* Nella prima tabella della pagina selezionare il download x64 a 32 bit x86 o a 64 bit, a seconda del sistema operativo in uso.
* Al termine del download, eseguire il programma di installazione.

![Download 7Zip](https://dotnet.microsoft.com/static/images/7-zip-downloads.png?v=W6qWtFC1tTMKv3YGXz7lBa9F3M22uWyTvkMmunyroNk)

### <a name="4-install-apache-spark"></a>4. installare Apache Spark

[Scaricare e installare Apache Spark](https://spark.apache.org/downloads.html). È necessario effettuare una selezione dalla versione 2,3. * o 2.4.0, 2.4.1, 2.4.3 o 2.4.4 (.NET per Apache Spark non è compatibile con le altre versioni di Apache Spark).

I comandi usati nei passaggi seguenti presuppongono che siano stati [scaricati e installati Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz). Se si vuole usare una versione diversa, sostituire **2.4.1** con il numero di versione appropriato. Estrarre quindi il file con estensione **tar** e i file di Apache Spark.

Per estrarre il file con **estensione tar** annidato:

* Individuare il file **Spark-2.4.1-bin-Hadoop 2.7. tgz** scaricato.
* Fare clic con il pulsante destro del mouse sul file e selezionare **7-zip-> estrarre qui**.
* **Spark-2.4.1-bin-Hadoop 2.7. tar** viene creato insieme al file **. tgz** scaricato.

Per estrarre i file di Apache Spark:

* Fare clic con il pulsante destro del mouse su **Spark-2.4.1-bin-Hadoop 2.7. tar** e selezionare **7-zip-> Estrai file...**
* Immettere **C:\bin** nel campo **Estrai** in.
* Deselezionare la casella di controllo sotto il campo **Estrai in** .
* Scegliere **OK**.
* I file Apache Spark vengono estratti in C:\bin\spark-2.4.1-bin-hadoop2.7\

![Installare Spark](https://dotnet.microsoft.com/static/images/spark-extract-with-7-zip.png?v=YvjUv54LIxI9FbALPC3h8zSQdyMtK2-NKbFOliG-f8M)

Eseguire i comandi seguenti per impostare le variabili di ambiente usate per individuare Apache Spark:

```console
setx HADOOP_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
setx SPARK_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
```

Dopo aver installato tutti gli elementi e impostato le variabili di ambiente, aprire un **nuovo** prompt dei comandi ed eseguire il comando seguente:

`%SPARK_HOME%\bin\spark-submit --version`

Se il comando esegue e stampa le informazioni sulla versione, è possibile passare al passaggio successivo.

Se viene visualizzato un messaggio di errore `'spark-submit' is not recognized as an internal or external command`, assicurarsi di aprire un **nuovo** prompt dei comandi.

### <a name="5-install-net-for-apache-spark"></a>5. installare .NET per Apache Spark

Scaricare la versione [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) da .net per Apache Spark github. Ad esempio, se si è in un computer Windows e si prevede di usare .NET Core, [scaricare la versione di Windows x64 netcoreapp 2.1](https://github.com/dotnet/spark/releases/download/v0.5.0/Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip).

Per estrarre Microsoft. Spark. Worker:

* Individuare il file **Microsoft. Spark. Worker. netcoreapp 2.1. Win-x64-0.6.0. zip** scaricato.
* Fare clic con il pulsante destro del mouse e selezionare **7-zip-> Estrai file...** .
* Immettere **C:\bin** nel campo **Estrai** in.
* Deselezionare la casella di controllo sotto il campo **Estrai in** .
* Scegliere **OK**.

![Installare .NET Spark](https://dotnet.microsoft.com/static/images/dotnet-for-spark-extract-with-7-zip.png?v=jwCyum9mL0mGIi4V5zC7yuvLfcj1_nL-QFFD8TClhZk)

### <a name="6-install-winutils"></a>6. installare file winutils

.NET per Apache Spark richiede l'installazione di file winutils insieme a Apache Spark. [Scaricare file winutils. exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe). Quindi, copiare file winutils in **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.

> [!NOTE]
> Se si usa una versione diversa di Hadoop, annotata alla fine del nome della cartella di installazione di Spark, [selezionare la versione di file winutils](https://github.com/steveloughran/winutils) compatibile con la versione di Hadoop.

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a>7. impostare DOTNET_WORKER_DIR e controllare le dipendenze

Eseguire il comando seguente per impostare la variabile di ambiente `DOTNET_WORKER_DIR`, che viene usata dalle app .NET per individuare .NET per Apache Spark:

`setx DOTNET_WORKER_DIR "C:\bin\Microsoft.Spark.Worker-0.6.0"`

Infine, verificare che sia possibile eseguire `dotnet`, `java`, `mvn``spark-shell` dalla riga di comando prima di passare alla sezione successiva.

## <a name="write-a-net-for-apache-spark-app"></a>Scrivere un'app .NET per Apache Spark

### <a name="1-create-a-console-app"></a>1. creare un'app console

Al prompt dei comandi eseguire i comandi seguenti per creare una nuova applicazione console:

```console
dotnet new console -o mySparkApp
cd mySparkApp
```

Il comando `dotnet` crea un'applicazione `new` di tipo `console` automaticamente. Il parametro `-o` crea una directory denominata *mySparkApp* in cui l'app viene archiviata e la popola con i file necessari. Il comando `cd mySparkApp` imposta la directory sulla directory dell'app appena creata.

### <a name="2-install-nuget-package"></a>2. installare il pacchetto NuGet

Per usare .NET per Apache Spark in un'app, installare il pacchetto Microsoft. Spark. Al prompt dei comandi eseguire il comando seguente:

`dotnet add package Microsoft.Spark --version 0.6.0`

### <a name="3-code-your-app"></a>3. scrivere un codice per l'app

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
            var spark = SparkSession
                .Builder()
                .AppName("word_count_sample")
                .GetOrCreate();

            // Create initial DataFrame.
            DataFrame dataFrame = spark.Read().Text("input.txt");

            // Count words.
            var words = dataFrame
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

### <a name="4-add-data-file"></a>4. aggiungere un file di dati

L'app elabora un file contenente righe di testo. Creare un file *input. txt* nella directory *mySparkApp* , contenente il testo seguente:

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

2. Eseguire il comando seguente per inviare l'applicazione da eseguire su Apache Spark:

   ```powershell
   %SPARK_HOME%\bin\spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local bin\Debug\netcoreapp3.0\microsoft-spark-2.4.x-0.6.0.jar dotnet bin\Debug\netcoreapp3.0\mySparkApp.dll
   ```

3. Quando l'app viene eseguita, i dati di conteggio delle parole del file *input. txt* vengono scritti nella console.

La procedura è stata completata. È stata creata ed eseguita un'app .NET per Apache Spark.

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione si è appreso come:
> [!div class="checklist"]
>
> * Preparare l'ambiente Windows per .NET per Apache Spark
> * Scrivere la prima applicazione .NET per Apache Spark
> * Creazione ed esecuzione di un'applicazione .NET semplice per Apache Spark

Per visualizzare un video che illustra i passaggi precedenti, vedere la [serie di video .NET per Apache Spark 101](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).

Per altre informazioni, vedere la pagina delle risorse.
> [!div class="nextstepaction"]
> [Risorse di .NET per Apache Spark](../resources/index.md)
