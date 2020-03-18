---
ms.openlocfilehash: 16ee73bfc0ab33b04ea3e2fa6d0eec521a9b8634
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78968071"
---
### <a name="resource-manifest-file-names"></a>Nomi dei file manifesto delle risorse

A partire da .NET Core 3.0, il nome del file manifesto della risorsa generato è stato modificato.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="change-description"></a>Descrizione modifica:

Prima di .NET Core 3.0, quando i metadati [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) venivano impostati per un file di risorse (*.resx*) nel file di progetto MSBuild, il nome del manifesto generato era *Namespace.Classname.resources*. Quando [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) non è stato impostato, il nome del manifesto generato è *Namespace.Classname.FolderPathRelativeToRoot.Culture.resources*.

A partire da .NET Core 3.0, quando un file *resx* viene collocato con un file di origine con lo stesso nome, ad esempio nelle app Windows Form, il nome del manifesto della risorsa viene generato dal nome completo del primo tipo nel file di origine. Ad esempio, se *Type.cs* è collocato tra *Type.resx*, il nome del manifesto generato è *Namespace.Classname.resources*. Tuttavia, se si modifica uno `EmbeddedResource` degli attributi della proprietà per il file *RESX,* il nome del file manifesto generato potrebbe essere diverso:

- Se `LogicalName` l'attributo nella `EmbeddedResource` proprietà è impostato, tale valore viene utilizzato come nome del file manifesto della risorsa.

  Esempi:

  ```xml
  <EmbeddedResource Include="X.resx" LogicalName="SomeName.resources" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" LogicalName="SomeName.resources" />
  ```

  **Nome del file manifesto**di risorsa generato : *SomeName.resources* (indipendentemente dal nome del file *RESX* o dalle impostazioni cultura o da qualsiasi altro metadati).

- Se `LogicalName` non è impostato, ma l'attributo `ManifestResourceName` della proprietà è impostato, il `EmbeddedResource` relativo valore, combinato con l'estensione di file *resources*, viene utilizzato come nome del file manifesto della risorsa.

  Esempi:

  ```xml
  <EmbeddedResource Include="X.resx" ManifestResourceName="SomeName" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" ManifestResourceName="SomeName.fr-FR" />
  ```

  **Nome del file manifesto della risorsa generato**: *SomeName.resources* o *SomeName.fr-FR.resources*.

- Se le regole precedenti non sono `DependentUpon` valide `EmbeddedResource` e l'attributo dell'elemento è impostato su un file di origine, il nome del tipo della prima classe nel file di origine viene utilizzato nel nome del file manifesto della risorsa. Più specificamente, il nome del file generato è *Namespace.Classname\[. Cultura].resources*.

  Esempi:

  ```xml
  <EmbeddedResource Include="X.resx" DependentUpon="MyTypes.cs">
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" DependentUpon="MyTypes.cs">
  ```

  Nome del manifesto della **risorsa generato:** *Namespace.Classname.resources* `Namespace.Classname` o *Namespace.Classname.fr-FR.resources* (dove è il nome della prima classe *nellMyTypes.cs*).

- Se le regole precedenti non `EmbeddedResourceUseDependentUponConvention` `true` sono applicabili, è (l'impostazione predefinita per .NET Core) e c'è un file di origine collocato con un file *RESX* con lo stesso nome di file di base, il file *RESX* viene reso dipendente dal file di origine corrispondente e il nome generato è lo stesso della regola precedente. Si tratta della regola "impostazioni predefinite" per i progetti .NET Core.This is the "default settings" rule for .NET Core projects.
  
  Esempi:
  
  I file *MyTypes.cs* e *MyTypes.resx* o *MyTypes.fr-FR.resx* sono presenti nella stessa cartella.
  
  Nome del manifesto della **risorsa generato:** *Namespace.Classname.resources* `Namespace.Classname` o *Namespace.Classname.fr-FR.resources* (dove è il nome della prima classe *nellMyTypes.cs*).

- Se nessuna delle regole precedenti è applicabile, il nome del file manifesto della risorsa generato è *RootNamespace.RelativePathWithDotsForSlashes.\[ Cultura.] risorse*. Il percorso relativo è `Link` il `EmbeddedResource` valore dell'attributo dell'elemento se è impostato. In caso contrario, il `Identity` percorso relativo è il valore dell'attributo dell'elemento. `EmbeddedResource` In Visual Studio, questo è il percorso dalla radice del progetto al file in Esplora soluzioni.

#### <a name="recommended-action"></a>Azione consigliata

Se non si è soddisfatti dei nomi di manifesto generati, è possibile:If you're insatisfied with the generated manifest names, you can:

- Modificare i metadati del file di risorse in base a una delle regole di denominazione descritte in precedenza.

- `EmbeddedResourceUseDependentUponConvention` Impostare `false` su nel file di progetto per rifiutare completamente esplicitamente la nuova convenzione:

   ```xml
   <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
   ```

   > [!NOTE]
   > Se `LogicalName` sono `ManifestResourceName` presenti gli attributi or, i relativi valori verranno comunque utilizzati per il nome del file generato.

#### <a name="category"></a>Category

MSBuild

#### <a name="affected-apis"></a>API interessate

N/D
