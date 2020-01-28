---
title: Spostarsi in un set di dati con il controllo BindingNavigator
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- datasets [Windows Forms], moving through
- BindingNavigator control [Windows Forms], moving through datasets
- examples [Windows Forms], BindingNavigator control
ms.assetid: 146d97be-3d97-400e-accb-860bbf47729d
ms.openlocfilehash: 73a102da74a3a2a00b5042331cffcaf3d858ea5b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742147"
---
# <a name="how-to-move-through-a-dataset-with-the-windows-forms-bindingnavigator-control"></a>Procedura: Esplorare un dataset con il controllo BindingNavigator Windows Form
Durante la creazione di applicazioni basate sui dati, è spesso necessario visualizzare raccolte di dati agli utenti. Il controllo <xref:System.Windows.Forms.BindingNavigator>, unitamente al componente <xref:System.Windows.Forms.BindingSource>, rappresenta una soluzione pratica e versatile per spostarsi all'interno di una raccolta e visualizzare gli elementi in sequenza.  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente illustra come usare un controllo <xref:System.Windows.Forms.BindingNavigator> per spostarsi all'interno dei dati. Il set è contenuto in una classe <xref:System.Data.DataView>, associata a un controllo <xref:System.Windows.Forms.TextBox> con un componente <xref:System.Windows.Forms.BindingSource>.  
  
> [!NOTE]
> L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione. L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro. Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md).  
  
 [!code-csharp[System.Windows.Forms.DataNavigator#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataNavigator#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System, System.Data, System.Drawing, System.Windows.Forms e System.Xml.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Controllo BindingNavigator](bindingnavigator-control-windows-forms.md)
- [Componente BindingSource](bindingsource-component.md)
- [Procedura: associare un controllo Windows Form a un tipo](how-to-bind-a-windows-forms-control-to-a-type.md)
