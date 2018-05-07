---
title: Cenni preliminari sul componente ErrorProvider (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- ErrorProvider
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error messages [Windows Forms], displaying
- ErrorProvider component [Windows Forms], about ErrorProvider component
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
ms.openlocfilehash: 2272220917f2d5adf15f1ba84a5d4c3d0ec07165
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="errorprovider-component-overview-windows-forms"></a>Cenni preliminari sul componente ErrorProvider (Windows Form)
Windows Form [ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-windows-forms.md) componente viene utilizzato per convalidare l'input dell'utente in un form o controllo. In genere utilizzato in combinazione con la convalida dell'input utente in un form o visualizzare gli errori all'interno di un set di dati. Un provider di errore è un'alternativa migliore rispetto alla visualizzazione di un messaggio di errore in una finestra di messaggio, perché una volta che viene chiusa una finestra di messaggio, il messaggio di errore non è più visibile. Il <xref:System.Windows.Forms.ErrorProvider> componente consente di visualizzare un'icona di errore (![icona ErrorProvider](../../../../docs/framework/winforms/controls/media/vberrorprovidericon.gif "vbErrorProviderIcon")) accanto al relativo controllo, ad esempio quando l'utente posiziona il puntatore del mouse su una casella di testo di icona di errore, una descrizione comandi verrà visualizzata la stringa di messaggio di errore.  
  
## <a name="key-properties"></a>Proprietà chiave  
 Il <xref:System.Windows.Forms.ErrorProvider> proprietà chiave del componente sono <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>, e <xref:System.Windows.Forms.ErrorProvider.Icon%2A>. Quando si utilizza <xref:System.Windows.Forms.ErrorProvider> componente con i controlli con associazione a dati, il <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> deve essere impostata su contenitore appropriato, in genere Windows Form, in ordine per il componente visualizzare un'icona di errore nel modulo. Quando il componente viene aggiunto nella finestra di progettazione, la <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> proprietà è impostata sul relativo form; se si aggiunge il controllo nel codice, è necessario impostarlo manualmente.  
  
 Il <xref:System.Windows.Forms.ErrorProvider.Icon%2A> proprietà può essere impostata su un'icona di errore personalizzato anziché il valore predefinito. Quando il <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> è impostata, il <xref:System.Windows.Forms.ErrorProvider> componente può visualizzare messaggi di errore per un set di dati. Il metodo chiave per la <xref:System.Windows.Forms.ErrorProvider> componente è il <xref:System.Windows.Forms.ErrorProvider.SetError%2A> (metodo), che specifica la stringa di messaggio di errore e in cui è visualizzata l'icona di errore.  
  
> [!NOTE]
>  Il <xref:System.Windows.Forms.ErrorProvider> componente non fornisce supporto incorporato per i client di accessibilità. Per rendere accessibile l'applicazione quando si utilizza questo componente, è necessario fornire un meccanismo di commenti e suggerimenti aggiuntivi, accessibile.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ErrorProvider>  
 [Procedura: Visualizzare errori in un dataset con il componente ErrorProvider di Windows Form](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)  
 [Procedura: Visualizzare le icone di errori per la convalida dei form con il componente ErrorProvider di Windows Form](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)
