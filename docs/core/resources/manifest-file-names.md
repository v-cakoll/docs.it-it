---
title: Modalità di generazione dei nomi dei file manifesto da MSBuild
description: Vengono descritti i fattori che influiscono sul nome di un file manifesto di risorsa generato da MSBuild in fase di compilazione.
ms.date: 05/08/2020
ms.topic: conceptual
ms.openlocfilehash: 383bf6a077b0631e70ddaa4721b20e992127a73c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83232326"
---
# <a name="how-resource-manifest-files-are-named"></a>Come vengono denominati i file manifesto delle risorse

Quando MSBuild compila un progetto .NET Core, i file di risorse XML con estensione *resx* sono convertiti in file con estensione *Resources* binari. I file binari sono incorporati nell'output del compilatore e possono essere letti da <xref:System.Resources.ResourceManager> . Questo articolo descrive il modo in cui MSBuild sceglie un nome per ogni file con *estensione resources* .

> [!TIP]
> Se si aggiunge un elemento di risorsa in modo esplicito al file di progetto ed è [incluso anche con il valore predefinito globs per .NET Core](../project-sdk/overview.md#default-compilation-includes), si otterrà un errore di compilazione. Per includere manualmente i file di risorse come `EmbeddedResource` elementi, impostare la `EnableDefaultEmbeddedResourceItems` proprietà su false.

## <a name="default-name"></a>Nome predefinito

In .NET Core 3,0 e versioni successive, il nome predefinito per un manifesto di risorsa viene usato quando vengono soddisfatte entrambe le condizioni seguenti:

- Il file di risorse non è incluso in modo esplicito nel file di progetto come `EmbeddedResource` elemento con i `LogicalName` `ManifestResourceName` metadati, o `DependentUpon` .
- La `EmbeddedResourceUseDependentUponConvention` proprietà non è impostata su `false` nel file di progetto. Per impostazione predefinita, questa proprietà è impostata su `true`. Per ulteriori informazioni, vedere [EmbeddedResourceUseDependentUponConvention](../project-sdk/msbuild-props.md#embeddedresourceusedependentuponconvention).

Se il file di risorse è condiviso con un file di origine (con*estensione cs* o *VB*) con lo stesso nome file radice, viene usato il nome completo del primo tipo definito nel file di origine per il nome del file manifesto. Se, ad esempio, `MyNamespace.Form1` è il primo tipo definito in *Form1.cs*e *Form1.cs* è colocato con *Form1. resx*, il nome del manifesto generato per il file di risorse è *MyNamespace. Form1. resources*.

## <a name="logicalname-metadata"></a>LogicalName (metadati)

Se un file di risorse viene incluso in modo esplicito nel file di progetto come un `EmbeddedResource` elemento con `LogicalName` metadati, il `LogicalName` valore viene usato come nome del manifesto. `LogicalName`ha la precedenza su qualsiasi altra impostazione o metadati.

Il nome del manifesto per il file di risorse definito nel frammento di file di progetto seguente è ad esempio *somename. resources*.

```xml
<EmbeddedResource Include="X.resx" LogicalName="SomeName.resources" />
```

-oppure-

```xml
<EmbeddedResource Include="X.fr-FR.resx" LogicalName="SomeName.resources" />
```

## <a name="manifestresourcename-metadata"></a>Metadati ManifestResourceName

Se un file di risorse viene incluso in modo esplicito nel file di progetto come un `EmbeddedResource` elemento con `ManifestResourceName` metadati (ed `LogicalName` è assente), il `ManifestResourceName` valore, combinato con l'estensione di file *. resources*, viene usato come nome del file manifesto.

Il nome del manifesto per il file di risorse definito nel frammento di file di progetto seguente è ad esempio *somename. resources*.

```xml
<EmbeddedResource Include="X.resx" ManifestResourceName="SomeName" />
```

Il nome del manifesto per il file di risorse definito nel frammento di file di progetto seguente è *somename.fr-fr. resources*.

```xml
<EmbeddedResource Include="X.fr-FR.resx" ManifestResourceName="SomeName.fr-FR" />
```

## <a name="dependentupon-metadata"></a>Metadati DependentUpon

Se un file di risorse viene incluso in modo esplicito nel file di progetto come un `EmbeddedResource` elemento con `DependentUpon` metadati (e `LogicalName` e non `ManifestResourceName` sono assenti), le informazioni del file di origine definito da vengono `DependentUpon` usate per il nome file del manifesto della risorsa. In particolare, il nome del primo tipo definito nel file di origine viene usato nel nome del manifesto come segue: *Namespace. NomeClasse \[ . Impostazioni cultura]. resources*.

Ad esempio, il nome del manifesto per il file di risorse definito nel frammento di file di progetto seguente è *Namespace. nomeclasse. resources* , dove `Namespace.Classname` è la prima classe definita in *myTypes.cs*.

```xml
<EmbeddedResource Include="X.resx" DependentUpon="MyTypes.cs">
```

Il nome del manifesto per il file di risorse definito nel frammento di file di progetto seguente è *Namespace.ClassName.fr-fr. resources* , dove `Namespace.Classname` è la prima classe definita in *myTypes.cs*.

```xml
<EmbeddedResource Include="X.fr-FR.resx" DependentUpon="MyTypes.cs">
```

## <a name="embeddedresourceusedependentuponconvention-property"></a>Proprietà EmbeddedResourceUseDependentUponConvention

Se `EmbeddedResourceUseDependentUponConvention` è impostato su `false` nel file di progetto, ogni nome di file del manifesto della risorsa è basato sullo spazio dei nomi radice per il progetto e sul percorso relativo dalla radice del progetto al file con *estensione resx* . In particolare, il nome del file manifesto della risorsa generato è *RootNamespace. RelativePathWithDotsForSlashes. \[ Impostazioni cultura.] risorse*. Si tratta anche della logica usata per generare i nomi di manifesto nelle versioni di .NET Core precedenti alla 3,0.

> [!NOTE]
>
> - Se `RootNamespace` non è definito, per impostazione predefinita viene impostato il nome del progetto.
> - Se `LogicalName` `ManifestResourceName` `DependentUpon` per un elemento del file di progetto si specificano i metadati, o `EmbeddedResource` , questa regola di denominazione non si applica al file di risorse.

## <a name="see-also"></a>Vedere anche

- [Funzionamento della denominazione delle risorse del manifesto](https://gist.github.com/BenVillalobos/041673b9a73bec60fdc3bf0f86fae62a)
- [Proprietà MSBuild per progetti .NET Core SDK](../project-sdk/msbuild-props.md)
- [Modifiche di rilievo di MSBuild](../compatibility/msbuild.md)
