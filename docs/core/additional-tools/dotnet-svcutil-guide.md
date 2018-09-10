---
title: Strumento Microsoft WCF dotnet-svcutil
description: Panoramica dello strumento Microsoft WCF dotnet-svcutil che aggiunge funzionalità per i progetti .NET Core e ASP.NET Core, come lo strumento WCF svcutil per i progetti .NET Framework.
author: mlacouture
ms.author: jralexander
ms.date: 08/20/2018
ms.openlocfilehash: bb4d8e5f3997318b720535b0f1e07fc33d13338a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43511886"
---
# <a name="microsoft-wcf-dotnet-svcutil-tool"></a>Strumento Microsoft WCF dotnet-svcutil

Lo strumento Windows Communication Foundation (WCF) **dotnet-svcutil** è uno strumento dell'interfaccia della riga di comando di .NET Core che consente di recuperare metadati da un servizio Web, in un percorso di rete o da un file WSDL e di generare una classe WCF contenente metodi del proxy client che accedono alle operazioni del servizio Web.

Analogo allo strumento [**Service Model Metadata - svcutil**](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per i progetti .NET Framework, **dotnet-svcutil** è uno strumento da riga di comando per la generazione di un riferimento al servizio Web compatibile con i progetti .NET Core e .NET Standard.

Lo strumento **dotnet-svcutil** rappresenta un'alternativa al provider di servizi connessi di Visuali Studio [**WCF Web Service Reference Provider**](wcf-web-service-reference-guide.md), disponibile per la prima volta con Visual Studio 2017 versione 15.5. Come strumento dell'interfaccia della riga di comando di .NET Core, **dotnet-svcutil** è disponibile come strumento multipiattaforma in Linux, macOS e Windows.

> [!IMPORTANT]
> Si consiglia di fare riferimento solo a servizi provenienti da un'origine attendibile. L'aggiunta di riferimenti da un'origine non attendibile può compromettere la sicurezza.

## <a name="prerequisites"></a>Prerequisiti

* [.NET Core SDK](https://www.microsoft.com/net/download) v1.0.4 o versioni successive
* Editor di codice preferito

## <a name="getting-started"></a>Per iniziare

L'esempio seguente illustra la procedura necessaria per aggiungere un riferimento al servizio Web a un progetto console .NET Core e richiamare il servizio. Si creerà un'applicazione console .NET Core denominata _HelloSvcutil_ e verrà aggiunto un riferimento a un servizio Web che implementa il contratto seguente:

```csharp
[ServiceContract]
public interface ISayHello
{
    [OperationContract]
    string Hello(string name);
}
```

In questo esempio si presuppone che il servizio Web sia ospitato all'indirizzo seguente: `http://contoso.com/SayHello.svc`

Da una finestra di comando di Windows, macOS o Linux eseguire la procedura seguente:

1. Creare una directory denominata _HelloSvcutil_ per il progetto e renderla la directory corrente, come nell'esempio seguente:

```console
mkdir HelloSvcutil
cd HelloSvcutil
```

2. Creare un nuovo progetto console C# in tale directory usando il comando [`dotnet new`](../tools/dotnet-new.md) come indicato di seguito:

```console
dotnet new console
```

3. Aprire il file di progetto `HelloSvcutil.csproj` nell'editor, modificare l'elemento `Project` e aggiungere il [`dotnet-svcutil` pacchetto NuGet](https://nuget.org/packages/dotnet-svcutil) come riferimento allo strumento dell'interfaccia della riga di comando, usando il codice seguente:

```xml
<ItemGroup>
  <DotNetCliToolReference Include="dotnet-svcutil" Version="1.0.*" />
</ItemGroup>
```

4. Ripristinare il pacchetto _dotnet-svcutil_ usando il comando [`dotnet restore`](../tools/dotnet-restore.md) come indicato di seguito:

```console
dotnet restore
```

5. Eseguire _dotnet_ con il comando _svcutil_ per generare il file di riferimento al servizio Web come indicato di seguito:

```console
dotnet svcutil http://contoso.com/SayHello.svc
```
Il file generato viene salvato come _HelloSvcutil/ServiceReference1/Reference.cs_. Lo strumento _dotnet_svcutil_ aggiunge inoltre al progetto i pacchetti WCF appropriati richiesti dal codice del proxy come riferimenti ai pacchetti.

6. Ripristinare i pacchetti WCF usando il comando [`dotnet restore`](../tools/dotnet-restore.md) come indicato di seguito:

```console
dotnet restore
```

7. Aprire il file `Program.cs` nell'editor, modificare il metodo `Main()` e sostituire il codice generato automaticamente con il codice seguente per richiamare il servizio Web:

```csharp
static void Main(string[] args)
{
    var client = new SayHelloClient();
    Console.WriteLine(client.HelloAsync("dotnet-svcutil").Result);
}
```

8. Eseguire l'applicazione usando il comando [`dotnet run`](../tools/dotnet-run.md) come indicato di seguito:

```console
dotnet run
```
Si dovrebbe vedere l'output seguente: "Hello dotnet-svcutil!"

Per una descrizione dettagliata dei parametri dello strumento `dotnet-svcutil`, richiamare lo strumento passando il parametro help come indicato di seguito:

```console
dotnet svcutil --help
```

## <a name="next-steps"></a>Passaggi successivi

### <a name="feedback--questions"></a>Commenti, suggerimenti e domande

In caso di domande o commenti e suggerimenti, [segnalare un problema in GitHub](https://github.com/dotnet/wcf/issues/new). È anche possibile rivedere domande o problemi esistenti [nel repository WCF in GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling).

### <a name="release-notes"></a>Note sulla versione

* Fare riferimento alle [note sulla versione](https://github.com/dotnet/wcf/blob/master/release-notes/dotnet-svcutil-notes.md) per informazioni aggiornate sulle versioni, compresi i problemi noti.

### <a name="information"></a>Informazioni

* [Pacchetto NuGet dotnet-svcutil](https://nuget.org/packages/dotnet-svcutil)
