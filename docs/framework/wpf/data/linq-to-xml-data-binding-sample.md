---
title: Esempio di data binding LINQ to XML
ms.date: 10/22/2019
ms.topic: sample
helpviewer_keywords:
- linq to xml data binding sample
ms.openlocfilehash: aac814e4768a863a93e69e34cd18c941a9b35c89
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920937"
---
# <a name="linq-to-xml-data-binding-sample"></a>Esempio di LINQ to XML data binding

Questo articolo descrive l'esempio LinqToXmlDataBinding, un'app Windows Presentation Foundation (WPF) che associa i componenti dell'interfaccia utente a un'origine dati XML incorporata.

## <a name="overview"></a>Panoramica

L'esempio LinqToXmlDataBinding è un'app Windows Presentation Foundation (WPF) che contiene C# i file di origine XAML e. Un documento XML incorporato definisce un elenco di libri. L'app consente all'utente di visualizzare, aggiungere, eliminare e modificare le voci del libro.

Sono disponibili due file di origine principali:

- [L2DBForm.xaml](l2dbform-xaml-source-code.md): contiene il codice della dichiarazione XAML per l'interfaccia utente della finestra principale. Contiene inoltre una sezione di risorse della finestra che definisce un provider di dati e un documento XML incorporato per gli elenchi di libri.

- [L2DBForm.xaml.cs](l2dbform-xaml-cs-source-code.md): contiene i metodi di inizializzazione e gestione eventi associati all'interfaccia utente.

La finestra principale è divisa nelle quattro sezioni di interfaccia utente verticali descritte di seguito:

- **XML**: visualizza l'origine XML non elaborata dell'elenco di libri incorporato.

- **Book List**: visualizza le voci relative ai libri come testo standard e consente all'utente di selezionare ed eliminare singole voci.

- **Edit Selected Book**: consente all'utente di modificare i valori associati alla voce attualmente selezionata.

- **Add New Book**: consente di creare una nuova voce in base ai valori immessi dall'utente.

## <a name="run-the-sample"></a>Eseguire l'esempio

Questa sezione illustra come creare e compilare il progetto LinqToXmlDataBinding in Visual Studio e come eseguire l'app LinqToXmlDataBinding Windows Presentation Foundation (WPF) risultante.

### <a name="create-the-project"></a>Creare il progetto

1. Aprire Visual Studio e creare un'**app WPF** in C# denominata **LinqToXmlDataBinding**.

   Il progetto dovrebbe avere come destinazione .NET Framework 3.5 (o versione successiva).

1. Se non sono già presenti, aggiungere i riferimenti di progetto per i seguenti assembly .NET:

    - System.Data
    - System.Data.DataSetExtensions
    - System.Xml
    - System.Xml

1. Compilare la soluzione premendo **CTRL**+**MAIUSC**+**B** ed eseguirla premendo **F5**.

   Il progetto dovrebbe essere compilato senza errori ed eseguito come applicazione WPF generica.

### <a name="add-code"></a>Aggiungi codice

1. In **Esplora soluzioni** rinominare il file di origine **Window1.xaml** in **L2XDBForm.xaml**.

   Il file di origine dipendente Window1.xaml.cs viene rinominato automaticamente in L2XDBForm.xaml.cs.

1. Sostituire il codice sorgente trovato nel file **L2XDBForm. XAML** con il [codice sorgente L2DBForm. XAML](l2dbform-xaml-source-code.md). Usare la visualizzazione Origine per usare questo file.

1. Analogamente, sostituire l'origine in **L2XDBForm.XAML.cs** con il [codice sorgente L2DBForm.XAML.cs](l2dbform-xaml-cs-source-code.md).

1. Nel file **app. XAML**sostituire tutte le occorrenze della stringa **Window1. XAML** con **L2XDBForm. XAML**.

1. Premere **CTRL**+**MAIUSC**+**B** per compilare la soluzione.

### <a name="run-the-app"></a>Eseguire l'app

L'app LinqToXmlDataBinding consente all'utente di visualizzare e modificare un elenco di libri archiviati come elemento XML incorporato. Eseguire l'app premendo **F5** (Avvia debug) o **CTRL**+**F5** (avvia senza eseguire debug).

Viene visualizzata una finestra con il titolo **WPF Data Binding using LINQ to XML** (Data binding WPF con LINQ to XML).

Nella sezione superiore dell'interfaccia utente viene visualizzato il **codice XML** non elaborato che rappresenta l'elenco di libri. Viene visualizzato tramite un controllo <xref:System.Windows.Controls.TextBlock> WPF che non consente l'interazione tramite mouse o tastiera.

Nella seconda sezione verticale, denominata **Book List**, vengono visualizzati i libri in un elenco ordinato in testo normale. Viene usato un controllo <xref:System.Windows.Controls.ListBox> che consente la selezione tramite mouse o tastiera.

### <a name="add-and-delete-books"></a>Aggiungere ed eliminare libri

Per aggiungere un nuovo libro all'elenco, immettere i valori nei controlli **ID** e **valore** <xref:System.Windows.Controls.TextBox> nell'ultima sezione, **Aggiungi nuovo libro**, quindi selezionare **Aggiungi libro**. Il libro viene aggiunto all'elenco sia nel libro che negli elenchi XML. In questo programma i valori di input non vengono convalidati.

Per eliminare un libro esistente dall'elenco, selezionarlo nella sezione **Book List** e quindi selezionare **Rimuovi book selezionato**. La voce del libro viene rimossa sia dal libro che dagli elenchi di origini XML non elaborate.

### <a name="edit-a-book-entry"></a>Modificare una voce di libro

1. Selezionare la voce del libro nella seconda sezione, **Book List**.

   I valori correnti vengono visualizzati nella sezione **Edit Selected Book** .

1. Modificare i valori usando la tastiera. Non appena <xref:System.Windows.Controls.TextBox> controllo perde lo stato attivo, le modifiche vengono propagate automaticamente all'origine XML e agli elenchi di libri.
