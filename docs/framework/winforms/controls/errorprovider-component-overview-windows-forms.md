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
ms.openlocfilehash: 8d6c509d8e603063309dada6f536c43b8ada5f6e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54591734"
---
# <a name="errorprovider-component-overview-windows-forms"></a>Cenni preliminari sul componente ErrorProvider (Windows Form)
I moduli di Windows [ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-windows-forms.md) componente viene usato per convalidare l'input dell'utente in un form o controllo. Viene in genere usato in combinazione con la convalida dell'input utente in un form o visualizzare gli errori all'interno di un set di dati. Un provider di errore è un'alternativa migliore rispetto alla visualizzazione di un messaggio di errore in una finestra di messaggio perché una volta che viene chiusa una finestra di messaggio, il messaggio di errore non è più visibile. Il <xref:System.Windows.Forms.ErrorProvider> componente consente di visualizzare un'icona di errore (![icona ErrorProvider](../../../../docs/framework/winforms/controls/media/vberrorprovidericon.gif "vbErrorProviderIcon")) accanto al relativo controllo, ad esempio una casella di testo; quando l'utente posiziona il puntatore del mouse su di icona di errore, una descrizione comando verrà visualizzata la stringa di messaggio di errore.  
  
## <a name="key-properties"></a>Proprietà chiave  
 Il <xref:System.Windows.Forms.ErrorProvider> sono proprietà di chiave del componente <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>, e <xref:System.Windows.Forms.ErrorProvider.Icon%2A>. Quando si usa <xref:System.Windows.Forms.ErrorProvider> componente con i controlli con associazione a dati, il <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> proprietà deve essere impostata per il contenitore appropriato (in genere il modulo di Windows) affinché il componente visualizzare un'icona di errore nel modulo. Quando il componente viene aggiunto nella finestra di progettazione, il <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> viene impostata al form contenitore; se si aggiunge il controllo nel codice, è necessario impostarlo manualmente.  
  
 Il <xref:System.Windows.Forms.ErrorProvider.Icon%2A> proprietà può essere impostata su un'icona di errore personalizzato anziché il valore predefinito. Quando la <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> è impostata, il <xref:System.Windows.Forms.ErrorProvider> componente può visualizzare i messaggi di errore per un set di dati. Il metodo principale del <xref:System.Windows.Forms.ErrorProvider> componente è il <xref:System.Windows.Forms.ErrorProvider.SetError%2A> (metodo), che consente di specificare la stringa di messaggio di errore e dove dovrebbe essere visualizzata l'icona di errore.  
  
> [!NOTE]
>  Il <xref:System.Windows.Forms.ErrorProvider> componente non fornisce supporto incorporato per i client di accessibilità. Per rendere accessibile l'applicazione quando si usa questo componente, è necessario fornire un meccanismo di commenti e suggerimenti aggiuntivi, accessibile.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.ErrorProvider>
- [Procedura: Visualizzare gli errori all'interno di un set di dati con il componente ErrorProvider di Windows Form](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)
- [Procedura: Visualizzare le icone di errore per la convalida dei Form con il componente ErrorProvider di Windows Form](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)
