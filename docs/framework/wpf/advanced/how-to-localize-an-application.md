---
title: Localizzare un'app
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- localization [WPF], applications
- LocBaml tool [WPF]
- applications [WPF], localizing
ms.assetid: 5001227e-9326-48a4-9dcd-ba1b89ee6653
ms.openlocfilehash: dc7d8f4f56b26fffbd883e1e1d6e420026e1f94f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209682"
---
# <a name="how-to-localize-an-application"></a>Procedura: localizzare un'applicazione

Questa esercitazione spiega come creare un'applicazione localizzata usando lo strumento LocBaml.  
  
> [!NOTE]
> Lo strumento LocBaml non è un'applicazione di produzione. Viene presentato come esempio in cui vengono usate alcune delle API di localizzazione e illustra come scrivere uno strumento di localizzazione.  
  
## <a name="overview"></a>Panoramica

Questo articolo offre un approccio dettagliato alla localizzazione di un'applicazione. Prima di tutto, preparare l'applicazione in modo che sia possibile estrarre il testo che verrà convertito. Dopo la traduzione del testo, il testo tradotto viene unito in una nuova copia dell'applicazione originale.
  
## <a name="create-a-sample-application"></a>Creare un'applicazione di esempio

In questo passaggio viene preparata l'applicazione per la localizzazione. Negli esempi Windows Presentation Foundation (WPF) viene fornito un esempio HelloApp che verrà usato per gli esempi di codice in questa discussione. Se si vuole usare questo esempio, scaricare i file di Extensible Application Markup Language (XAML) dall'esempio di [strumento LocBaml](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).  
  
1. Sviluppare l'applicazione fino al punto in cui si vuole iniziare la localizzazione.  
  
2. Specificare il linguaggio di sviluppo nel file di progetto in modo che MSBuild generi un assembly principale e un assembly satellite (un file con estensione resources. dll) per contenere le risorse della lingua neutra. Il file di progetto nell'esempio HelloApp è HelloApp.csproj. In questo file la lingua di sviluppo viene identificata come segue:  
  
   `<UICulture>en-US</UICulture>`  
  
3. Aggiungere gli UID ai file XAML. Gli UID vengono usati per rilevare le modifiche apportate ai file e per identificare gli elementi da convertire. Per aggiungere gli UID ai file, eseguire `updateuid` sul file di progetto:  

   `msbuild -t:updateuid helloapp.csproj`

   Per verificare che non siano presenti UID mancanti o duplicati, eseguire `checkuid` :  

   `msbuild -t:checkuid helloapp.csproj`

   Dopo `updateuid` l'esecuzione, i file devono contenere gli UID. Nel file *pane1. XAML* di HelloApp, ad esempio, dovrebbe essere presente quanto segue:  

   ```xaml
   <StackPanel x:Uid="StackPanel_1">
     <TextBlock x:Uid="TextBlock_1">Hello World</TextBlock>
     <TextBlock x:Uid="TextBlock_2">Goodbye World</TextBlock>
   </StackPanel>
   ```

## <a name="create-the-neutral-language-resources-satellite-assembly"></a>Creare l'assembly satellite per le risorse in lingua neutra

Quando l'applicazione viene configurata per generare un assembly satellite per le risorse di lingua neutra, l'applicazione viene compilata. Viene generato l'assembly principale dell'applicazione, nonché l'assembly satellite per le risorse di lingua neutra richiesto da LocBaml per la localizzazione.

Per compilare l'applicazione:  
  
1. Compilare HelloApp per creare una libreria di collegamento dinamico (DLL):  
  
   `msbuild helloapp.csproj`
  
2. L'assembly principale dell'applicazione appena creato, HelloApp. exe, viene creato nella cartella seguente: *C:\HelloApp\Bin\Debug*
  
3. L'assembly satellite delle risorse della lingua neutra appena creato, HelloApp. resources. dll, viene creato nella cartella seguente: *C:\HelloApp\Bin\Debug\en-US*
  
## <a name="build-the-locbaml-tool"></a>Compilare lo strumento LocBaml  
  
1. Tutti i file necessari per compilare LocBaml si trovano negli esempi di WPF. Scaricare i file C# dall' [esempio dello strumento LocBaml](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).  
  
2. Eseguire il file di progetto (LocBaml.csproj) per compilare lo strumento dalla riga di comando:  

   `msbuild locbaml.csproj`
  
3. Passare alla directory *bin\release* per trovare il file eseguibile appena creato (LocBaml. exe). Esempio: *C:\LocBaml\Bin\Release\locbaml.exe*
  
4. Di seguito sono riportate le opzioni che è possibile specificare quando si esegue LocBaml.

   | Opzione | Descrizione|
   | - | - |
   | `parse` o `-p` | Analizza il BAML, le risorse o i file DLL per generare un file CSV o txt. |
   | `generate` o `-g` | Genera un file binario localizzato utilizzando un file convertito. |
   | `out`o `-o` {*FileDirectory*] | Nome del file di output. |
   | `culture`o `-cul` {*culture*] | Impostazioni locali degli assembly di output. |
   | `translation`o `-trans` {*Translation. csv*] | File convertito o localizzato. |
   | `asmpath`o `-asmpath` {*FileDirectory*] | Se il codice XAML contiene controlli personalizzati, è necessario fornire all' `asmpath` assembly del controllo personalizzato. |
   | `nologo` |  non visualizza loghi o informazioni sul copyright. |
   | `verbose` |  visualizza le informazioni sulla modalità dettagliata. |
  
   > [!NOTE]
   > Se è necessario un elenco delle opzioni quando si esegue lo strumento, immettere `LocBaml.exe` e quindi premere **invio**.
  
## <a name="use-locbaml-to-parse-a-file"></a>Usare LocBaml per analizzare un file

Ora che è stato creato lo strumento LocBaml, è possibile usarlo per analizzare HelloApp.resources.dll ed estrarre il contenuto testuale che verrà localizzato.  
  
1. Copiare LocBaml.exe nella cartella bin\debug dell'applicazione in cui è stato creato l'assembly principale dell'applicazione.  
  
2. Per analizzare il file dell'assembly satellite e archiviare l'output come file CSV, usare il comando seguente:  
  
   `LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv`
  
   > [!NOTE]
   > Se il file di input, HelloApp.resources.dll, non è nella stessa directory di LocBaml.exe, spostare uno dei file in modo che entrambi siano nella stessa directory.  
  
3. Quando si esegue LocBaml per analizzare i file, l'output è costituito da sette campi delimitati da virgole (file CSV) o da tabulazioni (file TXT). Di seguito viene visualizzato il file CSV analizzato per HelloApp.resources.dll:

   | |
   |-|
   |HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;|
   |HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World|
   |HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World|

   I campi di sette sono:  
  
   - **Nome BAML**. Il nome della risorsa BAML rispetto all'assembly satellite per la lingua di origine.  
  
   - **Chiave di risorsa**. L'identificatore della risorsa localizzata.  
  
   - **Categoria**. Tipo di valore. Vedere [attributi e commenti di localizzazione](localization-attributes-and-comments.md).  
  
   - **Leggibilità**. Se il valore può essere letto da un localizzatore. Vedere [attributi e commenti di localizzazione](localization-attributes-and-comments.md).  
  
   - **Modificabilità**. Se il valore può essere modificato da un localizzatore. Vedere [attributi e commenti di localizzazione](localization-attributes-and-comments.md).  
  
   - **Commenti**. Descrizione aggiuntiva del valore per determinarne la modalità di localizzazione. Vedere [attributi e commenti di localizzazione](localization-attributes-and-comments.md).  
  
   - **Valore**. Il valore di testo da convertire nelle impostazioni cultura desiderate.  
  
   La tabella seguente mostra come viene eseguito il mapping di questi campi ai valori delimitati del file CSV:  
  
   |Nome BAML|Chiave di risorsa|Categoria|Leggibilità|Modificabilità|Commenti|valore|  
   |---------------|------------------|--------------|-----------------|-------------------|--------------|-----------|
   |HelloApp.g.en-US.resources:window1.baml|Stack1:System.Windows.Controls.StackPanel.$Content|Ignora|FALSE|FALSE||#Text1;#Text2|
   |HelloApp.g.en-US.resources:window1.baml|Text1:System.Windows.Controls.TextBlock.$Content|Nessuno|TRUE|TRUE||Hello World|
   |HelloApp.g.en-US.resources:window1.baml|Text2:System.Windows.Controls.TextBlock.$Content|Nessuno|TRUE|TRUE||Goodbye World|
  
   Si noti che tutti i valori per il campo **Commenti** non contengono valori. Se un campo non ha un valore, è vuoto. Si noti inoltre che l'elemento nella prima riga non è leggibile né modificabile e ha "Ignora" come valore di **categoria** , il che indica che il valore non è localizzabile.  
  
4. Per facilitare l'individuazione degli elementi localizzabili nei file analizzati, in particolare nei file di grandi dimensioni, è possibile ordinare o filtrare gli elementi per **categoria**, **leggibilità**e **modificabilità**. Ad esempio, è possibile escludere i valori non leggibili e non modificabili.  
  
## <a name="translate-the-localizable-content"></a>Tradurre il contenuto localizzabile

Usare gli strumenti disponibili per convertire il contenuto estratto. Per eseguire questa operazione, è possibile scrivere le risorse in un file con estensione CSV e visualizzarle in Microsoft Excel, in modo da apportare modifiche alla conversione nell'ultima colonna (valore).  
  
## <a name="use-locbaml-to-generate-a-new-resourcesdll-file"></a>Usare LocBaml per generare un nuovo file con estensione resources. dll

Il contenuto identificato analizzando HelloApp.resources.dll con LocBaml è stato convertito e deve essere reinserito nell'applicazione originale. Utilizzare l' `generate` `-g` opzione o per generare un nuovo file con estensione resources. dll.  
  
1. Usare la sintassi seguente per generare un nuovo file HelloApp.resources.dll. Contrassegnare le impostazioni cultura come en-US (/cul:en-US).  
  
   `LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US`  

   > [!NOTE]
   > Se il file di input Hello.csv non è presente nella stessa directory del file eseguibile LocBaml.exe, spostare uno dei file in modo che entrambi siano nella stessa directory.  
  
2. Sostituire il file *HelloApp. resources. dll* precedente nella directory *C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll* con il file *HelloApp. resources. dll* appena creato.  
  
3. Ora "Hello World" e "Goodbye World" possono essere convertiti nell'applicazione.  
  
4. Per eseguire la conversione in una lingua diversa, usare le impostazioni cultura della lingua in cui si sta eseguendo la conversione. L'esempio seguente mostra come eseguire la conversione in lingua francese canadese:  
  
   `LocBaml.exe /generate HelloApp.resources.dll /trans:Hellofr-CA.csv /out:c:\ /cul:fr-CA`  
  
5. Nello stesso assembly dell'assembly principale dell'applicazione, creare una nuova cartella specifica per le impostazioni cultura dove ospitare il nuovo assembly satellite. Per la lingua francese canadese, la cartella sarà fr-CA.  
  
6. Copiare l'assembly satellite generato nella nuova cartella.  
  
7. Per testare il nuovo assembly satellite, è necessario modificare le impostazioni cultura con cui verrà eseguita l'applicazione. Questa operazione può essere eseguita in due modi:  
  
   - Modificare le impostazioni internazionali del sistema operativo.
  
   - Aggiungere il codice seguente al file App.xaml.cs nell'applicazione:  
  
     [!code-xaml[LocBamlChangeCultureSnippets#LocBamlChangeCultureMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml#locbamlchangeculturemarkup)]
     [!code-csharp[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml.cs#locbamlchangeculturecodebehind)]
     [!code-vb[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/VisualBasic/Application.xaml.vb#locbamlchangeculturecodebehind)]  
  
## <a name="tips-for-using-locbaml"></a>Suggerimenti per l'uso di LocBaml  
  
- Tutti gli assembly dipendenti che definiscono i controlli personalizzati devono essere copiati nella directory locale di LocBaml o installati in Global Assembly Cache. Questa operazione è necessaria perché l'API di localizzazione deve avere accesso agli assembly dipendenti quando legge il codice XAML binario (BAML).  
  
- Se l'assembly principale è firmato, anche la DLL di risorse generata deve essere firmata per poter essere caricata.  
  
- La versione della DLL di risorsa localizzata deve essere sincronizzata con l'assembly principale.
  
## <a name="see-also"></a>Vedere anche

- [Globalizzazione per WPF](globalization-for-wpf.md)
- [Cenni preliminari sull'utilizzo del layout automatico](use-automatic-layout-overview.md)
