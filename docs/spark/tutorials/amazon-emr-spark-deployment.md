---
title: Distribuire un'applicazione .NET per Apache Spark in Amazon EMR Spark
description: Informazioni su come distribuire un'applicazione .NET per Apache Spark in Amazon EMR Spark.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: a1ff1ba4d5e855e0ac36b99b0c9d63adfaaaac1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73454940"
---
# <a name="deploy-a-net-for-apache-spark-application-to-amazon-emr-spark"></a>Distribuire un'applicazione .NET per Apache Spark in Amazon EMR Spark

Questa esercitazione illustra come distribuire un'applicazione .NET per Apache Spark in Amazon EMR Spark.

In questa esercitazione verranno illustrate le procedure per:

> [!div class="checklist"]
>
> * Preparare Microsoft.Spark.Worker
> * Pubblicare l'app Spark .NET
> * Distribuire l'app in Amazon EMR Spark
> * Eseguire l'app

## <a name="prerequisites"></a>Prerequisites

Prima di iniziare, eseguire le operazioni seguenti:

* Scaricare l'[interfaccia della riga di comando di AWS](https://aws.amazon.com/cli/).
* Scaricare [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) nel computer locale. Si tratta di uno script helper che verrà usato in seguito per copiare i file dipendenti di .NET per Apache Spark nei nodi di lavoro del cluster Spark.

## <a name="prepare-worker-dependencies"></a>Preparare le dipendenze dei nodi di lavoro

**Microsoft.Spark.Worker** è un componente back-end che si trova nei singoli nodi di lavoro del cluster Spark. Quando si vuole eseguire una funzione definita dall'utente C#, Spark deve comprendere come avviare CLR .NET per eseguire la funzione definita dall'utente. **Microsoft. Spark.Worker** offre una raccolta di classi per Spark che consentono di abilitare questa funzionalità.

1. Selezionare una versione netcoreapp Linux di [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) da distribuire nel cluster.

   Ad esempio, se si vuole usare `.NET for Apache Spark v0.1.0` con `netcoreapp2.1`, scaricare [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).

2. Caricare `Microsoft.Spark.Worker.<release>.tar.gz` e [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) in un file system distribuito (ad esempio, S3) a cui può accedere il cluster.

## <a name="prepare-your-net-for-apache-spark-app"></a>Preparare .NET per l'app Apache Spark

1. Per creare l'app, seguire l'esercitazione [Introduzione](get-started.md).

2. Pubblicare l'app Spark .NET come indipendente.

   Eseguire il comando seguente in Linux.

   ```dotnetcli
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. Produrre `<your app>.zip` per i file pubblicati.

   Eseguire il comando seguente in Linux con `zip`.

   ```bash
   zip -r <your app>.zip .
   ```

4. Caricare gli elementi seguenti in un file system distribuito (ad esempio, S3) a cui può accedere il cluster:

   * `microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: questo jar è incluso come parte del pacchetto [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet e viene collocato nella directory di output di compilazione dell'app.
   * `<your app>.zip`
   * I file (come i file di dipendenza o i dati comuni accessibili a ogni ruolo di lavoro) o gli assembly (ad esempio le DLL che contengono funzioni definite dall'utente o librerie da cui dipende l'app), vengono inseriti nella directory di lavoro di ogni executor.

## <a name="deploy-to-amazon-emr-spark"></a>Distribuire in Amazon EMR Spark

[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) è una piattaforma cluster gestita che semplifica l'esecuzione di framework per Big Data in AWS.

> [!NOTE]
> Amazon EMR Spark è basato su Linux. Se si è interessati a distribuire l'app in Amazon EMR Spark, pertanto, assicurarsi che l'app sia compatibile con .NET Standard e che venga usato il [compilatore .NET Core](https://dotnet.microsoft.com/download) per compilare l'app.

### <a name="deploy-microsoftsparkworker"></a>Distribuire Microsoft.Spark.Worker

Questo passaggio è necessario solo in fase di creazione del cluster.

Eseguire `install-worker.sh` durante la creazione del cluster usando [azioni bootstrap](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html).

Eseguire il comando seguente in Linux usando l'interfaccia della riga di comando di AWS.

```bash
aws emr create-cluster \
--name "Test cluster" \
--release-label emr-5.23.0 \
--use-default-roles \
--ec2-attributes KeyName=myKey \
--applications Name=Spark \
--instance-count 3 \
--instance-type m1.medium \
--bootstrap-actions Path=s3://mybucket/<some dir>/install-worker.sh,Name="Install Microsoft.Spark.Worker",Args=["aws","s3://mybucket/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz","/usr/local/bin"]
```

## <a name="run-your-app"></a>Eseguire l'app

Per eseguire l'app in Amazon EMR Spark, è possibile procedere in due modi: spark-submit e Amazon EMR Steps.

### <a name="use-spark-submit"></a>Usare spark-submit

È possibile usare il comando [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) per inviare processi .NET per Apache Spark ad Amazon EMR Spark.

1. `ssh` in uno dei nodi nel cluster.

2. Eseguire `spark-submit`.

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   s3://mybucket/<some dir>/<your app>.zip <your app> <app args>
   ```

### <a name="use-amazon-emr-steps"></a>Usare Amazon EMR Steps

È possibile usare [Amazon EMR Steps](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) per inviare i processi al framework Spark installato nel cluster EMR.

Eseguire il comando seguente in Linux usando l'interfaccia della riga di comando di AWS.

```bash
aws emr add-steps \
--cluster-id j-xxxxxxxxxxxxx \
--steps Type=spark,Name="Spark Program",Args=[--master,yarn,--files,s3://mybucket/<some dir>/<udf assembly>,--class,org.apache.spark.deploy.dotnet.DotnetRunner,s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar,s3://mybucket/<some dir>/<your app>.zip,<your app>,<app arg 1>,<app arg 2>,...,<app arg n>],ActionOnFailure=CONTINUE
```

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stata distribuita un'applicazione .NET per Apache Spark in Amazon EMR Spark. Per esaminare progetti di esempio di .NET per Apache Spark, passare a GitHub.

> [!div class="nextstepaction"]
> [.NET for Apache Spark samples](https://github.com/dotnet/spark/tree/master/examples) (Esempi di .NET per Apache Spark)
