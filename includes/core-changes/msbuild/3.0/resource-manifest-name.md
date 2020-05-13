---
ms.openlocfilehash: f24a29a00a1bff34a452c43716d76bf72ef277b5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206220"
---
### <a name="resource-manifest-file-name-change"></a>Modifica del nome del file manifesto della risorsa

A partire da .NET Core 3,0, nel caso predefinito, MSBuild genera un nome di file manifesto diverso per i file di risorse.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="change-description"></a>Descrizione modifica:

Prima di .NET Core 3,0, se `LogicalName` `ManifestResourceName` `DependentUpon` per un elemento nel file di progetto non è stato specificato alcun metadati, o `EmbeddedResource` , MSBuild ha generato un nome di file manifesto nel criterio `<RootNamespace>.<ResourceFilePathFromProjectRoot>.resources` . Se `RootNamespace` non è definito nel file di progetto, per impostazione predefinita viene impostato il nome del progetto. Ad esempio, il nome del manifesto generato per un file di risorse denominato *Form1. resx* nella directory del progetto radice è *MyProject. Form1. resources*.

A partire da .NET Core 3,0, se un file di risorse è posizionato con un file di origine con lo stesso nome, ad esempio *Form1. resx* e *Form1.cs*, MSBuild usa le informazioni sul tipo del file di origine per generare il nome del file manifesto nel modello `<Namespace>.<ClassName>.resources` . Lo spazio dei nomi e il nome della classe vengono estratti dal primo tipo nel file di origine con percorso condiviso. Ad esempio, il nome del manifesto generato per un file di risorse denominato *Form1. resx* che si trova in un file di origine denominato *Form1.cs* è *MyNamespace. Form1. resources*. La cosa importante da notare è che la prima parte del nome file è diversa rispetto alle versioni precedenti di .NET Core (*MyNamespace* anziché *MyProject*).

> [!NOTE]
> Se si dispone `LogicalName` di `ManifestResourceName` metadati, o `DependentUpon` specificati in un `EmbeddedResource` elemento nel file di progetto, questa modifica non influisce sul file di risorse.

Questa modifica di rilievo è stata introdotta con l'aggiunta della `EmbeddedResourceUseDependentUponConvention` proprietà ai progetti .NET Core. Per impostazione predefinita, i file di risorse non sono elencati in modo esplicito in un file di progetto .NET Core, quindi non hanno `DependentUpon` metadati per specificare come assegnare un nome al file con *estensione resources* generato. Quando `EmbeddedResourceUseDependentUponConvention` è impostato su `true` , ovvero il valore predefinito, MSBuild cerca un file di origine con percorso condiviso ed estrae uno spazio dei nomi e un nome di classe da tale file. Se si imposta `EmbeddedResourceUseDependentUponConvention` su `false` , MSBuild genera il nome del manifesto in base al comportamento precedente, che combina `RootNamespace` e il percorso del file relativo.

#### <a name="recommended-action"></a>Azione consigliata

Nella maggior parte dei casi, non è richiesta alcuna azione da parte dello sviluppatore e l'app dovrebbe continuare a funzionare. Tuttavia, se questa modifica interrompe l'app, è possibile eseguire una delle operazioni seguenti:

- Modificare il codice in modo che preveda il nuovo nome del manifesto.

- Rifiutare esplicitamente la nuova convenzione di denominazione impostando `EmbeddedResourceUseDependentUponConvention` su `false` nel file di progetto.

  ```xml
  <PropertyGroup>
    <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
  </PropertyGroup>
  ```

#### <a name="category"></a>Categoria

MSBuild

#### <a name="affected-apis"></a>API interessate

N/D
