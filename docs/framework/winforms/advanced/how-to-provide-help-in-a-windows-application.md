---
title: 'Procedura: Visualizzare la Guida in un''applicazione Windows'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Help [Windows Forms], Windows applications
- HTML Help [Windows Forms], Windows Forms
- Windows applications [Windows Forms], providing Help
- HelpProvider component [Windows Forms]
- forms [Windows Forms], providing Help
ms.assetid: 7c4e5cec-2bd2-4f0b-8d75-c2b88929bd61
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0f407f1c17c67ec99f4499b89c49932a4ba6d32c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-provide-help-in-a-windows-application"></a>Procedura: Visualizzare la Guida in un'applicazione Windows
È possibile utilizzare il <xref:System.Windows.Forms.HelpProvider> componente per collegare gli argomenti della Guida all'interno di un file della Guida in controlli specifici in Windows Form. Il file della Guida può essere in formato HTML o HTMLHelp 1. x o versione successiva.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-provide-help"></a>Per visualizzare la Guida  
  
1.  Dal **della casella degli strumenti**, trascinare un <xref:System.Windows.Forms.HelpProvider> componente al form.  
  
     Il componente verrà posizionato sulla barra delle applicazioni in basso in Progettazione Windows Form.  
  
2.  Nel **proprietà** finestra, impostare il <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> proprietà al file della Guida con estensione chm, col o htm.  
  
3.  Selezionare un altro controllo, si dispone sul form e nel **proprietà** finestra, impostare il <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> proprietà.  
  
     Questa è la stringa passata attraverso il <xref:System.Windows.Forms.HelpProvider> componente al file della Guida per richiamare l'argomento della Guida appropriato.  
  
4.  Nel **proprietà** finestra, impostare il <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> un valore di proprietà il <xref:System.Windows.Forms.HelpNavigator> enumerazione.  
  
     Questa impostazione determina il modo in cui la proprietà **HelpKeyword** viene passata al sistema della Guida. La tabella seguente elenca le impostazioni possibili e le relative descrizioni.  
  
    |Nome del membro|Descrizione|  
    |-----------------|-----------------|  
    |AssociateIndex|Specifica che l'indice di un argomento specificato viene eseguito nell'URL specificato.|  
    |Find|Specifica che viene visualizzata la pagina di ricerca di un URL specificato.|  
    |Indice|Specifica che viene visualizzato l'indice di un URL specificato.|  
    |KeywordIndex|Specifica una parola chiave da cercare e l'azione da eseguire nell'URL specificato.|  
    |TableOfContents|Specifica che viene visualizzato il sommario del file della Guida HTML 1.0.|  
    |Argomento|Specifica che viene visualizzato l'argomento a cui fa riferimento l'URL specificato.|  
  
 In fase di esecuzione, premere F1 quando il controllo, per cui impostare il **HelpKeyword** e **HelpNavigator** proprietà, ovvero ha lo stato attivo verrà aperto il file della Guida che è associata <xref:System.Windows.Forms.HelpProvider> componente.  
  
 Attualmente, la proprietà **HelpNamespace** supporta i file della Guida nei tre formati seguenti: HTMLHelp 1.x, HTMLHelp 2.0 e HTML. Pertanto, è possibile impostare la proprietà **HelpNamespace** su un indirizzo http://, ad esempio una pagina Web. In tal caso, nel browser predefinito verrà visualizzata la pagina Web con la stringa specificata nella proprietà **HelpKeyword** usata come ancoraggio. L'ancoraggio viene usato per passare direttamente a una parte specifica di una pagina HTML.  
  
> [!IMPORTANT]
>  Assicurarsi di verificare tutte le informazioni inviate da un client prima di usarle nell'applicazione, dal momento che utenti malintenzionati potrebbero tentare di inviare script eseguibili, istruzioni SQL o altro codice. Prima di visualizzare l'input di un utente, archiviarlo in un database o usarlo, assicurarsi che non contenga informazioni potenzialmente pericolose. Un modo per effettuare questo controllo consiste nell'usare un'espressione regolare per cercare parole chiave come "SCRIPT" quando si riceve input da un utente.  
  
 È inoltre possibile utilizzare il <xref:System.Windows.Forms.HelpProvider> componente per visualizzare la Guida rapida, anche se è stato configurato per visualizzare i file della Guida per i controlli in Windows Form. Per altre informazioni, vedere [Procedura: Visualizzare la Guida rapida](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Visualizzare la Guida rapida](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)  
 [Visualizzazione della Guida relativa a un controllo tramite le descrizioni comandi](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)  
 [Integrazione della Guida dell'utente in Windows Form](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)  
 [Windows Form](../../../../docs/framework/winforms/index.md)
