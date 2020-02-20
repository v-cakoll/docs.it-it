---
ms.openlocfilehash: 276268d31670b5e7dcd0ae9c0b7a61c3c38ca663
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451889"
---
### <a name="resource-manifest-file-names"></a>Nomi file manifesto delle risorse

A partire da .NET Core 3,0, il nome del file manifesto della risorsa generato è stato modificato.

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="change-description"></a>Descrizione della modifica

Prima di .NET Core 3,0, quando venivano impostati i metadati [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) per un file di risorse (*resx*) nel file di progetto MSBuild, il nome del manifesto generato era *Namespace. nomeclasse. resources*. Quando [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) non è stato impostato, il nome del manifesto generato è *Namespace. nomeclasse. FolderPathRelativeToRoot. culture. resources*.

A partire da .NET Core 3,0, quando un file con *estensione resx* è condiviso con un file di origine con lo stesso nome, ad esempio in Windows Forms app, il nome del manifesto della risorsa viene generato dal nome completo del primo tipo nel file di origine. Se, ad esempio, *Type.cs* è condiviso con *Type. resx*, il nome del manifesto generato è *Namespace. nomeclasse. resources*. Tuttavia, se si modifica uno degli attributi della proprietà `EmbeddedResource` per il file con *estensione resx* , il nome del file manifesto generato potrebbe essere diverso:

- Se viene impostato l'attributo `LogicalName` della proprietà `EmbeddedResource`, tale valore viene usato come nome del file manifesto della risorsa.

  Esempi:

  ```xml
  <EmbeddedResource Include="X.resx" LogicalName="SomeName.resources" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" LogicalName="SomeName.resources" />
  ```

  **Nome file manifesto risorsa generato**: *somename. resources* (indipendentemente dal nome del file con *estensione resx* o dalle impostazioni cultura o da altri metadati).

- Se `LogicalName` non è impostato, ma viene impostato l'attributo `ManifestResourceName` nella proprietà `EmbeddedResource`, il relativo valore, combinato con l'estensione di file *. resources*, viene usato come nome file del manifesto della risorsa.

  Esempi:

  ```xml
  <EmbeddedResource Include="X.resx" ManifestResourceName="SomeName" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" ManifestResourceName="SomeName.fr-FR" />
  ```

  **Nome file manifesto risorsa generato**: *somename. resources* o *somename.fr-fr. resources*.

- Se non si applicano le regole precedenti e l'attributo `DependentUpon` sull'elemento `EmbeddedResource` è impostato su un file di origine, nel nome del file manifesto della risorsa viene usato il nome del tipo della prima classe nel file di origine. In particolare, il nome del file generato è *Namespace. nomeclasse\[. Impostazioni cultura]. resources*.

  Esempi:

  ```xml
  <EmbeddedResource Include="X.resx" DependentUpon="MyTypes.cs">
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" DependentUpon="MyTypes.cs">
  ```

  **Nome file manifesto risorsa generato**: *Namespace. nomeclasse. resources* o *Namespace.ClassName.fr-fr. resources* (dove `Namespace.Classname` è il nome della prima classe in *myTypes.cs*).

- Se non si applicano le regole precedenti, `EmbeddedResourceUseDependentUponConvention` è `true` (impostazione predefinita per .NET Core) ed è presente un file di origine con un file con estensione *resx* con lo stesso nome file di base, il file con *estensione resx* viene reso dipendente dal file di origine corrispondente e il nome generato è identico a quello della regola precedente. Si tratta della regola "impostazioni predefinite" per i progetti .NET Core.
  
  Esempi:
  
  I file *myTypes.cs* e *types. resx* o *myTypes.fr-fr. resx* sono presenti nella stessa cartella.
  
  **Nome file manifesto risorsa generato**: *Namespace. nomeclasse. resources* o *Namespace.ClassName.fr-fr. resources* (dove `Namespace.Classname` è il nome della prima classe in *myTypes.cs*).
    
- Se nessuna delle regole precedenti è applicabile, il nome del file manifesto della risorsa generato è *RootNamespace. RelativePathWithDotsForSlashes.\[impostazioni cultura.] risorse*. Il percorso relativo è il valore dell'attributo `Link` dell'elemento `EmbeddedResource` se è impostato. In caso contrario, il percorso relativo è il valore dell'attributo `Identity` dell'elemento `EmbeddedResource`. In Visual Studio è il percorso dalla radice del progetto al file in Esplora soluzioni.

#### <a name="recommended-action"></a>Azione consigliata

Se non si è soddisfatti dei nomi dei manifesti generati, è possibile:

- Modificare i metadati del file di risorse in base a una delle regole di denominazione descritte in precedenza.

- Impostare `EmbeddedResourceUseDependentUponConvention` su `false` nel file di progetto per rifiutare esplicitamente la nuova convenzione:

   ```xml
   <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
   ```

   > [!NOTE]
   > Se sono presenti gli attributi `LogicalName` o `ManifestResourceName`, i relativi valori verranno comunque utilizzati per il nome del file generato.

#### <a name="category"></a>Category

MSBuild

#### <a name="affected-apis"></a>API interessate

N/D
