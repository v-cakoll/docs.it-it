---
title: Creazione del pacchetto e distribuzione delle estensioni My personalizzate
ms.date: 08/14/2018
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
ms.openlocfilehash: a2e2a6705fb3d8d4424d46d96bbf49b41e1414af
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330253"
---
# <a name="package-and-deploy-custom-my-extensions-visual-basic"></a>Pacchetto e distribuzione delle estensioni My personalizzate (Visual Basic)

Visual Basic fornisce un modo semplice per distribuire le estensioni dello spazio `My` dei nomi personalizzate utilizzando i modelli di Visual Studio. Se si sta creando un modello di progetto per il `My` quale le estensioni sono parte integrante del nuovo tipo di progetto, è possibile includere il `My` codice di estensione personalizzato con il progetto quando si esporta il modello. Per altre informazioni sull'esportazione di modelli di progetto, vedere [procedura: creare modelli di progetto](/visualstudio/ide/how-to-create-project-templates).

Se l'estensione `My` personalizzata si trova in un unico file di codice, è possibile esportare il file come modello di elemento che gli utenti possono aggiungere a qualsiasi tipo di Visual Basic progetto. È quindi possibile personalizzare il modello di elemento per abilitare funzionalità e comportamenti aggiuntivi per l' `My` estensione personalizzata in un progetto Visual Basic. Di seguito sono riportate alcune funzionalità:

- Consentire agli utenti di gestire l' `My` estensione personalizzata dalla pagina **estensioni My** di progettazione progetti Visual Basic.

- Aggiunta automatica dell'estensione `My` personalizzata quando un riferimento a un assembly specificato viene aggiunto a un progetto.

- Nascondere il `My` modello di elemento di estensione nella finestra di dialogo **Aggiungi elemento** in modo che non sia incluso nell'elenco di elementi del progetto.

In questo argomento viene illustrato come creare un `My` pacchetto di un'estensione personalizzata come modello di elemento nascosto che può essere gestito dalla pagina **estensioni My** della finestra di progettazione del progetto Visual Basic. L'estensione `My` personalizzata può inoltre essere aggiunta automaticamente quando un riferimento a un assembly specificato viene aggiunto a un progetto.

## <a name="create-a-my-namespace-extension"></a>Creare un'estensione per lo spazio dei nomi My

Il primo passaggio nella creazione di un pacchetto di distribuzione per `My` un'estensione personalizzata consiste nel creare l'estensione come singolo file di codice. Per informazioni dettagliate e istruzioni su come creare un'estensione `My` personalizzata, vedere [estensione dello spazio dei nomi My in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).

## <a name="export-a-my-namespace-extension-as-an-item-template"></a>Esportare un'estensione dello spazio dei nomi My come modello di elemento

Quando si dispone di un file di codice che `My` include l'estensione dello spazio dei nomi, è possibile esportare il file di codice come modello di elemento di Visual Studio. Per istruzioni su come esportare un file come modello di elemento di Visual Studio, vedere [procedura: creare modelli di elementi](/visualstudio/ide/how-to-create-item-templates).

> [!NOTE]
> Se l' `My` estensione dello spazio dei nomi ha una dipendenza da un assembly specifico, è possibile personalizzare il modello di elemento `My` per installare automaticamente l'estensione dello spazio dei nomi quando viene aggiunto un riferimento a tale assembly. Sarà quindi necessario escludere il riferimento all'assembly quando si esporta il file di codice come modello di elemento di Visual Studio.

## <a name="customize-the-item-template"></a>Personalizzare il modello di elemento

È possibile abilitare il modello di elemento per la gestione dalla pagina **estensioni My** della finestra di progettazione del progetto Visual Basic. È anche possibile abilitare l'aggiunta automatica del modello di elemento quando un riferimento a un assembly specificato viene aggiunto a un progetto. Per abilitare queste personalizzazioni, si aggiungerà un nuovo file, denominato file CustomData, al modello e quindi si aggiungerà un nuovo elemento al file XML nel file con estensione vstemplate.

### <a name="add-the-customdata-file"></a>Aggiungere il file CustomData

Il file CustomData è un file di testo con estensione del nome di file. CustomData (il nome del file può essere impostato su qualsiasi valore significativo per il modello) e che contiene XML. Il codice XML nel file CustomData indica Visual Basic di includere l' `My` estensione quando gli utenti usano la pagina **estensioni My** della finestra di progettazione del progetto Visual Basic. Facoltativamente, è possibile aggiungere l' `AssemblyFullName>` attributo <al file XML del file CustomData. In questo modo si indica Visual Basic di installare automaticamente `My` l'estensione personalizzata quando un riferimento a un assembly specifico viene aggiunto al progetto. È possibile usare qualsiasi editor di testo o editor XML per creare il file CustomData e quindi aggiungerlo alla cartella compressa del modello di elemento (file zip).

Il codice XML seguente, ad esempio, Mostra il contenuto di un file CustomData che aggiungerà l'elemento del modello alla cartella My Extensions di un progetto Visual Basic quando un riferimento all'assembly Microsoft. VisualBasic. PowerPacks. vs. dll viene aggiunto al progetto.

```xml
<VBMyExtensionTemplate
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"
    Version="1.0.0.0"
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"
/>
```

Il file CustomData contiene un elemento `VBMyExtensionTemplate>` <con attributi elencati nella tabella seguente.

|Attributo|Description|
|---|---|
|`ID`|Obbligatorio. Identificatore univoco per l'estensione. Se l'estensione con questo ID è già stata aggiunta al progetto, all'utente non verrà richiesto di aggiungerla di nuovo.|
|`Version`|Obbligatorio. Numero di versione per il modello di elemento.|
|`AssemblyFullName`|Facoltativo. Nome dell'assembly. Quando un riferimento a questo assembly viene aggiunto al progetto, all'utente viene richiesto di aggiungere l' `My` estensione da questo modello di elemento.|

### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a>Aggiungere l' \<elemento CustomDataSignature> al file con estensione vstemplate

Per identificare il modello di elemento di Visual Studio `My` come estensione dello spazio dei nomi, è necessario modificare anche il file vstemplate per il modello di elemento. È necessario aggiungere un `<CustomDataSignature>` elemento all' `<TemplateData>` elemento. L' `<CustomDataSignature>` elemento deve contenere il testo `Microsoft.VisualBasic.MyExtension`, come illustrato nell'esempio seguente.

```xml
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>
```

Non è possibile modificare direttamente i file in una cartella compressa (file con estensione zip). È necessario copiare il file con estensione vstemplate dalla cartella compressa, modificarlo e quindi sostituire il file con estensione vstemplate nella cartella compressa con la copia aggiornata.

Nell'esempio seguente viene illustrato il contenuto di un file con estensione vstemplate per `<CustomDataSignature>` il quale è stato aggiunto l'elemento.

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

Per installare il modello, è possibile copiare la cartella compressa (file*zip* ) nella cartella dei modelli di elemento Visual Basic. Per impostazione predefinita, i modelli di elemento utente si trovano in *%USERPROFILE%\Documents\Visual Studio \<\>versione \Templates\ItemTemplates\Visual di base*. In alternativa, è possibile pubblicare il modello come file di Programma di installazione di Visual Studio (*VSI*).

## <a name="see-also"></a>Vedi anche

- [Estensione dello spazio dei nomi My in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)
- [Estensione del modello di applicazione Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
- [Personalizzazione degli oggetti disponibili in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [Pagina Estensioni My, Creazione progetti](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
