---
title: Tagliare le applicazioni autonome
description: Scopri come tagliare le app autonome per ridurne le dimensioni. .NET Core raggruppa il runtime con un'app pubblicata in modo autonomo e in genere include più tempo di runtime.
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: bb8ac88c5e16b7fd20a7670e4ad76dbe4b44da1b
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242912"
---
# <a name="trim-self-contained-deployments-and-executables"></a>Trimming delle distribuzioni autonome e degli eseguibili

Quando si pubblica un'applicazione autonoma, il runtime di .NET Core viene fornito insieme all'applicazione. Questo raggruppamento aggiunge una quantità significativa di contenuto all'applicazione in pacchetto. Quando si tratta di distribuire l'applicazione, le dimensioni sono spesso un fattore importante. Mantenere le dimensioni dell'applicazione del pacchetto il più piccolo possibile è in genere un obiettivo per gli sviluppatori di applicazioni.

A seconda della complessità dell'applicazione, è necessario solo un sottoinsieme del runtime per eseguire l'applicazione. Queste parti inutilizzate del runtime non sono necessarie e possono essere tagliate dall'applicazione in pacchetto.

La funzionalità di taglio funziona esaminando i file binari dell'applicazione per individuare e compilare un grafico degli assembly di runtime necessari. Gli assembly di runtime rimanenti a cui non viene fatto riferimento sono esclusi.

> [!NOTE]
> Il taglio è una funzionalità sperimentale in .NET Core 3.1 ed è disponibile _solo_ per le applicazioni pubblicate autonome.

## <a name="prevent-assemblies-from-being-trimmed"></a>Impedire la rifila degli assiemi

Esistono scenari in cui la funzionalità di taglio non riuscirà a rilevare i riferimenti. Ad esempio, quando la reflection viene utilizzata in un assembly di runtime, dall'applicazione o da una libreria a cui fa riferimento l'applicazione, all'assembly non viene fatto riferimento direttamente. Il taglio non è a conoscenza di questi riferimenti indiretti ed escludela dalla cartella pubblicata.

Quando il codice fa riferimento indirettamente a un assembly tramite reflection, `<TrimmerRootAssembly>` è possibile impedire che l'assembly venga tagliato con l'impostazione. Nell'esempio seguente viene illustrato `System.Security` come impedire che un assieme denominato assembly venga tagliato:

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="trim-your-app---cli"></a>Tagliare l'app - CLI

Tagliare l'applicazione utilizzando il comando [dotnet publish.](../tools/dotnet-publish.md) Quando pubblichi l'app, imposta le tre impostazioni seguenti:

- Pubblica come autonomo:`--self-contained true`
- Disabilitare la pubblicazione su file singolo:`-p:PublishSingleFile=false`
- Abilita taglio:`p:PublishTrimmed=true`

L'esempio seguente pubblica un'app per Windows 10 come autonoma e taglia l'output.

```dotnetcli
dotnet publish -c Release -r win10-x64 --self-contained true -p:PublishSingleFile=false -p:PublishTrimmed=true
```

Per altre informazioni, vedere [Pubblicare app .NET Core con l'interfaccia della riga di comando di .NET Core .NET .](deploy-with-cli.md)

## <a name="trim-your-app---visual-studio"></a>Tagliare il taglio dell'app - Visual Studio

Visual Studio crea profili di pubblicazione riutilizzabili che controllano la modalità di pubblicazione dell'applicazione.

01. Nel riquadro **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto che si desidera pubblicare. Selezionare **Pubblica...**.

    :::image type="content" source="media/trim-self-contained/visual-studio-solution-explorer.png" alt-text="Esplora soluzioni con un menu di scelta rapida che evidenzia l'opzione Pubblica.Solution Explorer with a right-click menu highlighting the Publish option.":::

    Se non si dispone già di un profilo di pubblicazione, seguire le istruzioni per crearne uno e scegliere il tipo di destinazione **Cartella.**

01. Scegliere **Modifica**.

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-edit-settings.png" alt-text="Profilo di pubblicazione di Visual Studio con pulsante Modifica.":::

01. Nella finestra di dialogo **Impostazioni profilo,** impostare le seguenti opzioni:

    - Impostare **Modalità di distribuzione** su **Self-contained**.
    - Impostare Runtime di **destinazione** sulla piattaforma in cui si desidera eseguire la pubblicazione.
    - Selezionare **Taglia assiemi inutilizzati (in anteprima)**.

    Scegliere **Salva** per salvare le impostazioni e tornare alla finestra di dialogo **Pubblica.**

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-properties.png" alt-text="Finestra di dialogo Impostazioni profilo con la modalità di distribuzione, il runtime di destinazione e le opzioni di taglio degli assiemi inutilizzati evidenziate.":::

01. Scegliere **Pubblica** per pubblicare l'app tagliata.

Per ulteriori informazioni, consultate [Pubblicare app .NET Core con Visual Studio.](deploy-with-vs.md)

## <a name="trim-your-app---visual-studio-for-mac"></a>Tagliare il taglio dell'app - Visual Studio per Mac

Visual Studio per Mac non fornisce opzioni per tagliare l'app durante la pubblicazione. Dovrai pubblicare manualmente seguendo le istruzioni della sezione [Tagliare l'app - CLI.](#trim-your-app---cli) Per altre informazioni, vedere [Pubblicare app .NET Core con l'interfaccia della riga di comando di .NET Core .NET .](deploy-with-cli.md)

## <a name="see-also"></a>Vedere anche

- [Distribuzione dell'applicazione .NET Core](index.md).
- [Pubblicare app .NET Core con l'interfaccia della riga di comando di .NET Core.](deploy-with-cli.md)
- [Pubblicare app .NET Core con Visual Studio](deploy-with-vs.md).
- [dotnet comando di pubblicazione](../tools/dotnet-publish.md).
