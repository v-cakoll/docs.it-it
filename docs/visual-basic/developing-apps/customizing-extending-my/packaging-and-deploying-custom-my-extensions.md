---
title: Assemblaggio e distribuzione delle estensioni My (Visual Basic) personalizzate
ms.date: 08/14/2018
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
ms.openlocfilehash: 4212f58c39f63be6ba20c3b79e5d9c98d0615c5e
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43745373"
---
# <a name="package-and-deploy-custom-my-extensions-visual-basic"></a>Il pacchetto e distribuire personalizzata delle estensioni My (Visual Basic)

Visual Basic fornisce un modo semplice la distribuzione personalizzata `My` estensioni spazio dei nomi con i modelli di Visual Studio. Se si sta creando un modello di progetto per il quale il `My` le estensioni sono parte integrante del nuovo tipo di progetto, è possibile includere solo personalizzata `My` codice dell'estensione per il progetto quando si esporta il modello. Per altre informazioni sull'esportazione di modelli di progetto, vedere [procedura: creare modelli di progetto](/visualstudio/ide/how-to-create-project-templates).

Se personalizzata `My` estensione è in un singolo file di codice, è possibile esportare il file come modello di elemento che possono essere aggiunte a qualsiasi tipo di progetto Visual Basic. È quindi possibile personalizzare il modello di elemento per abilitare funzionalità aggiuntive e il comportamento per personalizzata `My` estensione in un progetto Visual Basic. Tali funzionalità includono quanto segue:

- Consentire agli utenti di gestire personalizzata `My` estensione dal **estensioni My** pagina della finestra di progettazione di progetto Visual Basic.

- Aggiunta automatica personalizzati `My` estensione quando un riferimento a un assembly specificato viene aggiunto a un progetto.

- Nascondendo il `My` modello di elemento di estensione nel **Aggiungi elemento** finestra di dialogo in modo che non è incluso nell'elenco di elementi di progetto.

Questo argomento viene illustrato come creare un pacchetto personalizzato `My` estensione come un modello di elemento nascosti che può essere gestito dal **estensioni My** pagina della finestra di progettazione di progetto Visual Basic. L'oggetto personalizzato `My` estensione può inoltre aggiunti automaticamente quando viene aggiunto a un progetto un riferimento a un assembly specificato.

## <a name="create-a-my-namespace-extension"></a>Creare una My extension dello spazio dei nomi

Il primo passaggio nella creazione di un pacchetto di distribuzione per un oggetto personalizzato `My` estensione consiste nel creare l'estensione come un singolo file di codice. Per informazioni dettagliate e informazioni aggiuntive su come creare una classe personalizzata `My` estensione, vedere [estendendo il Namespace My in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).

## <a name="export-a-my-namespace-extension-as-an-item-template"></a>Esportare una My extension dello spazio dei nomi come un modello di elemento

Dopo aver creato un file di codice che include il `My` estensione dello spazio dei nomi, è possibile esportare il file di codice come un modello di elemento di Visual Studio. Per istruzioni su come esportare un file come un modello di elemento di Visual Studio, vedere [procedura: creare modelli di elementi](/visualstudio/ide/how-to-create-item-templates).

> [!NOTE]
> Se il `My` estensione dello spazio dei nomi presenta una dipendenza da un particolare assembly, è possibile personalizzare il modello di elemento per installare automaticamente il `My` estensione dello spazio dei nomi quando viene aggiunto un riferimento a tale assembly. Di conseguenza, è consigliabile escludere tale riferimento all'assembly quando si esporta il file di codice come un modello di elemento di Visual Studio.

## <a name="customize-the-item-template"></a>Personalizzare il modello di elemento

È possibile abilitare il modello di elemento essere gestiti dal **estensioni My** pagina della finestra di progettazione di progetto Visual Basic. È anche possibile abilitare il modello di elemento che verrà aggiunta automaticamente quando viene aggiunto a un progetto un riferimento a un assembly specificato. Per abilitare queste personalizzazioni, si verrà aggiungere un nuovo file, chiamato CustomData, al modello e quindi aggiungere un nuovo elemento al codice XML nel file con estensione vstemplate.

### <a name="add-the-customdata-file"></a>Aggiungere il file. CustomData

Il file CustomData è un file di testo con un'estensione di. CustomData (il nome del file può essere impostato su un valore significativo al modello) e che contiene XML. Il codice XML nel file di CustomData indica a Visual Basic per includere il `My` estensione quando gli utenti usano i **estensioni My** pagina della finestra di progettazione di progetto Visual Basic. È possibile aggiungere facoltativamente il <`AssemblyFullName>` dell'attributo XML del file CustomData. Indica a Visual Basic per l'installazione automatica personalizzato `My` estensione quando un riferimento a un determinato assembly viene aggiunto al progetto. È possibile usare qualsiasi editor di testo o editor XML per creare il file CustomData e quindi aggiungerlo alla cartella compressa del modello di elemento (file con estensione zip).

Ad esempio, il codice XML seguente mostra il contenuto di un file di CustomData che verrà aggiunto l'elemento di modello nella cartella estensioni personali di un progetto di Visual Basic quando un riferimento all'assembly Microsoft.VisualBasic.PowerPacks.Vs.dll viene aggiunto al progetto.

```xml
<VBMyExtensionTemplate
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"
    Version="1.0.0.0"
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"
/>
```

Il file di CustomData contiene una <`VBMyExtensionTemplate>` elemento che ha gli attributi elencati nella tabella seguente.

|Attributo|Descrizione|
|---|---|
|`ID`|Obbligatorio. Identificatore univoco per l'estensione. Se l'estensione con questo ID è già stato aggiunto al progetto, l'utente non richiederà aggiungerlo nuovamente.|
|`Version`|Obbligatorio. Un numero di versione per il modello di elemento.|
|`AssemblyFullName`|Facoltativo. Nome dell'assembly. Quando un riferimento a questo assembly viene aggiunto al progetto, l'utente verrà richiesto di aggiungere il `My` estensione da questo modello di elemento.|

### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a>Aggiungere il \<CustomDataSignature > elemento del file con estensione vstemplate

Per identificare il modello di elemento di Visual Studio come un `My` estensione dello spazio dei nomi, è anche necessario modificare il file con estensione vstemplate per il modello di elemento. È necessario aggiungere un `<CustomDataSignature>` elemento per il `<TemplateData>` elemento. Il `<CustomDataSignature>` elemento deve contenere il testo `Microsoft.VisualBasic.MyExtension`, come illustrato nell'esempio seguente.

```xml
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>
```

Non è possibile modificare direttamente i file in una cartella compressa (zip). È necessario copiare il file con estensione vstemplate dalla cartella compressa, modificarlo e quindi sostituire il file con estensione vstemplate nella cartella compressa con la copia aggiornata.

L'esempio seguente mostra il contenuto di un file con estensione vstemplate che contiene il `<CustomDataSignature>` elemento aggiunto.

```xml
<VSTemplate Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Item">
  <TemplateData>
    <DefaultName>MyCustomExtensionModule.vb</DefaultName>
    <Name>MyPrinterInfo</Name>
    <Description>Custom My Extensions Item Template</Description>
    <ProjectType>VisualBasic</ProjectType>
    <SortOrder>10</SortOrder>
    <Icon>__TemplateIcon.ico</Icon>
    <CustomDataSignature      >Microsoft.VisualBasic.MyExtension</CustomDataSignature>
  </TemplateData>
  <TemplateContent>
    <References />
    <ProjectItem SubType="Code"
                 TargetFileName="$fileinputname$.vb"
                 ReplaceParameters="true"
     >MyCustomExtensionModule.vb</ProjectItem>
  </TemplateContent>
</VSTemplate>
```

## <a name="install-the-template"></a>Installare il modello

Per installare il modello, è possibile copiare la cartella compressa (*zip* file) nella cartella dei modelli di elemento Visual Basic. Per impostazione predefinita, i modelli di elemento utente si trovano *%USERPROFILE%\Documents\Visual Studio \<versione\>\Templates\ItemTemplates\Visual Basic*. In alternativa, è possibile pubblicare il modello come un programma di installazione di Visual Studio (*vsi*) file.

## <a name="see-also"></a>Vedere anche

- [Estensione dello spazio dei nomi My in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)
- [Estensione del modello di applicazione Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
- [Personalizzazione degli oggetti disponibili in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [Pagina Estensioni My, Creazione progetti](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
