---
title: "Procedura: Visualizzare la Guida in un'applicazione Windows"
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], Windows applications
- HTML Help [Windows Forms], Windows Forms
- Windows applications [Windows Forms], providing Help
- HelpProvider component [Windows Forms]
- forms [Windows Forms], providing Help
ms.assetid: 7c4e5cec-2bd2-4f0b-8d75-c2b88929bd61
ms.openlocfilehash: 405de333ce936a864047e827e60f56a930059e26
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84143628"
---
# <a name="how-to-provide-help-in-a-windows-application"></a>Procedura: Visualizzare la Guida in un'applicazione Windows

È possibile utilizzare il <xref:System.Windows.Forms.HelpProvider> componente per alleghi gli argomenti della Guida in un file della guida a controlli specifici in Windows Forms. Il file della Guida può essere in formato HTML o HTMLHelp 1. x o versione successiva.

## <a name="provide-help"></a>Fornire la guida

1. In Visual Studio trascinare un componente dalla **casella degli strumenti** <xref:System.Windows.Forms.HelpProvider> al form.

     Il componente verrà posizionato sulla barra delle applicazioni in basso in Progettazione Windows Form.

2. Nella finestra **Proprietà** impostare la proprietà sul <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> file della guida con estensione chm, col o htm.

3. Selezionare un altro controllo sul form, quindi nella finestra **Proprietà** impostare la <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> Proprietà.

     Si tratta della stringa passata tramite il <xref:System.Windows.Forms.HelpProvider> componente al file della Guida per richiamare l'argomento della Guida appropriato.

4. Nella finestra **Proprietà** impostare la <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> proprietà su un valore dell' <xref:System.Windows.Forms.HelpNavigator> enumerazione.

     Questa impostazione determina il modo in cui la proprietà **HelpKeyword** viene passata al sistema della Guida. La tabella seguente elenca le impostazioni possibili e le relative descrizioni.

    |Nome membro|Descrizione|
    |-----------------|-----------------|
    |AssociateIndex|Specifica che l'indice di un argomento specificato viene eseguito nell'URL specificato.|
    |Trova|Specifica che viene visualizzata la pagina di ricerca di un URL specificato.|
    |Indice|Specifica che viene visualizzato l'indice di un URL specificato.|
    |KeywordIndex|Specifica una parola chiave da cercare e l'azione da eseguire nell'URL specificato.|
    |TableOfContents|Specifica che viene visualizzato il sommario del file della Guida HTML 1.0.|
    |Argomento|Specifica che viene visualizzato l'argomento a cui fa riferimento l'URL specificato.|

 In fase di esecuzione, premendo F1 quando il controllo, per il quale sono state impostate le proprietà **HelpKeyword** e **HelpNavigator** , lo stato attivo consente di aprire il file della Guida associato a tale <xref:System.Windows.Forms.HelpProvider> componente.

 Attualmente, la proprietà **HelpNamespace** supporta i file della Guida nei tre formati seguenti: HTMLHelp 1.x, HTMLHelp 2.0 e HTML. Pertanto, è possibile impostare la proprietà **HelpNamespace** su un `http://` Indirizzo, ad esempio una pagina Web. In tal caso, nel browser predefinito verrà visualizzata la pagina Web con la stringa specificata nella proprietà **HelpKeyword** usata come ancoraggio. L'ancoraggio viene usato per passare direttamente a una parte specifica di una pagina HTML.

> [!IMPORTANT]
> Assicurarsi di verificare tutte le informazioni inviate da un client prima di usarle nell'applicazione, dal momento che utenti malintenzionati potrebbero tentare di inviare script eseguibili, istruzioni SQL o altro codice. Prima di visualizzare l'input di un utente, archiviarlo in un database o usarlo, assicurarsi che non contenga informazioni potenzialmente pericolose. Un modo per effettuare questo controllo consiste nell'usare un'espressione regolare per cercare parole chiave come "SCRIPT" quando si riceve input da un utente.

È anche possibile usare il <xref:System.Windows.Forms.HelpProvider> componente per visualizzare la Guida popup, anche se è stato configurato per visualizzare i file della Guida per i controlli nel Windows Forms. Per altre informazioni, vedere [Procedura: Visualizzare la Guida rapida](how-to-display-pop-up-help.md).

## <a name="see-also"></a>Vedi anche

- [Procedura: Visualizzare la Guida rapida](how-to-display-pop-up-help.md)
- [Visualizzazione della Guida relativa a un controllo tramite le descrizioni comandi](control-help-using-tooltips.md)
- [Integrazione della Guida dell'utente in Windows Form](integrating-user-help-in-windows-forms.md)
- [Windows Forms](../index.md)
