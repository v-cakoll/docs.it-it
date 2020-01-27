---
title: Cenni preliminari sul componente ErrorProvider
ms.date: 03/30/2017
f1_keywords:
- ErrorProvider
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error messages [Windows Forms], displaying
- ErrorProvider component [Windows Forms], about ErrorProvider component
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
ms.openlocfilehash: b66e97d97d0d8c2ea4e9bdba29f8ff35e486e1f6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745795"
---
# <a name="errorprovider-component-overview-windows-forms"></a>Cenni preliminari sul componente ErrorProvider (Windows Form)
Il componente Windows Forms [ErrorProvider](errorprovider-component-windows-forms.md) viene usato per convalidare l'input dell'utente in un form o un controllo. Viene in genere usato in combinazione con la convalida dell'input dell'utente in un form o la visualizzazione di errori all'interno di un set di dati. Un provider di errori è un'alternativa migliore rispetto alla visualizzazione di un messaggio di errore in una finestra di messaggio, perché quando una finestra di messaggio viene rilasciata, il messaggio di errore non è più visibile. Il componente <xref:System.Windows.Forms.ErrorProvider> Visualizza un'icona di errore (![un punto esclamativo bianco all'interno di un cerchio rosso.](./media/errorprovider-component-overview-windows-forms/vb-error-provider-icon.gif)) accanto al controllo pertinente, ad esempio una casella di testo; Quando l'utente posiziona il puntatore del mouse sull'icona di errore, viene visualizzata una descrizione comando che mostra la stringa del messaggio di errore.  
  
## <a name="key-properties"></a>Proprietà chiave  
 Le proprietà chiave del componente <xref:System.Windows.Forms.ErrorProvider> sono <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>e <xref:System.Windows.Forms.ErrorProvider.Icon%2A>. Quando si usa <xref:System.Windows.Forms.ErrorProvider> componente con controlli associati a dati, è necessario impostare la proprietà <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> sul contenitore appropriato, in genere Windows Form, per consentire al componente di visualizzare un'icona di errore nel form. Quando il componente viene aggiunto nella finestra di progettazione, la proprietà <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> viene impostata sul form che lo contiene; Se si aggiunge il controllo nel codice, è necessario impostarlo manualmente.  
  
 La proprietà <xref:System.Windows.Forms.ErrorProvider.Icon%2A> può essere impostata su un'icona di errore personalizzata anziché sul valore predefinito. Quando viene impostata la proprietà <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, il componente <xref:System.Windows.Forms.ErrorProvider> può visualizzare i messaggi di errore per un set di dati. Il metodo principale del componente <xref:System.Windows.Forms.ErrorProvider> è il metodo <xref:System.Windows.Forms.ErrorProvider.SetError%2A>, che specifica la stringa del messaggio di errore e il punto in cui deve essere visualizzata l'icona di errore.  
  
> [!NOTE]
> Il componente <xref:System.Windows.Forms.ErrorProvider> non fornisce supporto incorporato per i client di accessibilità. Per rendere l'applicazione accessibile quando si utilizza questo componente, è necessario fornire un meccanismo aggiuntivo di feedback accessibile.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ErrorProvider>
- [Procedura: Visualizzare errori in un dataset con il componente ErrorProvider di Windows Form](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
- [Procedura: Visualizzare le icone di errori per la convalida dei form con il componente ErrorProvider di Windows Form](display-error-icons-for-form-validation-with-wf-errorprovider.md)
