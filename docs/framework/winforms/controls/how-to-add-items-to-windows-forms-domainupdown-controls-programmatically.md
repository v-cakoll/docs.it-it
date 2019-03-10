---
title: 'Procedura: Aggiungere elementi ai controlli DomainUpDown di Windows Form a livello di codice'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- spin button control [Windows Forms], adding items
- DomainUpDown control [Windows Forms], adding items to
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
ms.openlocfilehash: 06c2c83ddfba67aaff775065cc2aa4515978bf81
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722711"
---
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a>Procedura: Aggiungere elementi ai controlli DomainUpDown di Windows Form a livello di codice
È possibile aggiungere elementi ai moduli di Windows <xref:System.Windows.Forms.DomainUpDown> nel codice. Chiamare il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> o <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> metodo per il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> classe per aggiungere elementi al controllo <xref:System.Windows.Forms.DomainUpDown.Items%2A> proprietà. Il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> metodo aggiunge un elemento alla fine di una raccolta, mentre il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> metodo aggiunge un elemento in una posizione specificata.  
  
### <a name="to-add-a-new-item"></a>Per aggiungere un nuovo elemento  
  
1.  Usare il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> metodo per aggiungere un elemento alla fine dell'elenco di elementi.  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     -oppure-  
  
2.  Usare il <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> metodo per inserire un elemento nell'elenco in una posizione specificata.  
  
    ```vb  
    ' Inserts an item at the third position in the list  
    DomainUpDown1.Items.Insert(2, "rice")  
    ```  
  
    ```csharp  
    // Inserts an item at the third position in the list  
    domainUpDown1.Items.Insert(2, "rice");  
    ```  
  
    ```cpp  
    // Inserts an item at the third position in the list  
    domainUpDown1->Items->Insert(2, "rice");  
    ```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>
- [Controllo DomainUpDown](domainupdown-control-windows-forms.md)
- [Panoramica sul controllo DomainUpDown](domainupdown-control-overview-windows-forms.md)
