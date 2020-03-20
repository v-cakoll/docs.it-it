---
title: Aggiunta di informazioni per l'Accesso facilitato ai controlli in un Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, accessibility
- controls [Windows Forms], accessibility
- accessibility [Windows Forms], Windows Forms controls
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 887dee6f-5059-4d57-957d-7c6fcd4acb10
ms.openlocfilehash: 672104db94826cfbe113a7ae0ea29546b0c3b9da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182004"
---
# <a name="providing-accessibility-information-for-controls-on-a-windows-form"></a>Aggiunta di informazioni per l'Accesso facilitato ai controlli in un Windows Form
Gli strumenti per l'accessibilità sono dispositivi e programmi specializzati che consentono agli utenti con disabilità di usare i computer in modo più efficace. Sono incluse, ad esempio, le utilità per la lettura dello schermo per gli utenti non vedenti e le utilità di input vocale per le persone che usano i comandi vocali anziché il mouse o la tastiera. Gli strumenti per l'accessibilità interagiscono con le proprietà di accessibilità esposte dai controlli Windows Form. Le proprietà sono riportate di seguito:  
  
- **AccessibilityObject**  
  
- **AccessibleDefaultActionDescription**  
  
- **AccessibleDescription**  
  
- **AccessibleName**  
  
- **AccessibleRole**  
  
## <a name="accessibilityobject-property"></a>Proprietà AccessibilityObject  
 Questa proprietà di sola lettura contiene un'istanza della <xref:System.Windows.Forms.AccessibleObject> . **AccessibleObject** implementa l'interfaccia <xref:Accessibility.IAccessible> , che fornisce informazioni sulla descrizione del controllo, la posizione sullo schermo, le capacità di spostamento e il valore. La finestra di progettazione imposta questo valore quando il controllo viene aggiunto al form.  
  
## <a name="accessibledefaultactiondescription-property"></a>Proprietà AccessibleDefaultActionDescription  
 Questa stringa descrive l'azione del controllo. Non è visualizzata nella finestra Proprietà e può essere impostata solo nel codice. L'esempio seguente mostra come impostare questa proprietà per un pulsante:  
  
```vb  
Button1.AccessibleDefaultActionDescription = _  
   "Closes the application."  
```

```csharp  
Button1.AccessibleDefaultActionDescription =
   "Closes the application.";  
```

```cpp  
button1->AccessibleDefaultActionDescription =  
   "Closes the application.";  
```  
  
## <a name="accessibledescription-property"></a>Proprietà AccessibleDescription  
 Questa stringa descrive il controllo. Può essere impostata nella finestra Proprietà o nel codice, come illustrato di seguito:  
  
```vb  
Button1.AccessibleDescription = "A button with text 'Exit'."  
```

```csharp  
Button1.AccessibleDescription = "A button with text 'Exit'";  
```

```cpp  
button1->AccessibleDescription = "A button with text 'Exit'";  
```  
  
## <a name="accessiblename-property"></a>Proprietà AccessibleName  
 Questa stringa rappresenta il nome di un controllo segnalato agli strumenti di accessibilità. Può essere impostata nella finestra Proprietà o nel codice, come illustrato di seguito:  
  
```vb  
Button1.AccessibleName = "Order"  
```

```csharp  
Button1.AccessibleName = "Order";  
```

```cpp  
button1->AccessibleName = "Order";  
```  
  
## <a name="accessiblerole-property"></a>Proprietà AccessibleRole  
 Questa proprietà, che contiene una <xref:System.Windows.Forms.AccessibleRole> descrive il ruolo di interfaccia utente del controllo. Per un nuovo controllo il valore è impostato su `Default`. Ciò significa che, per impostazione predefinita, un controllo **Button** si comporta come un **pulsante**. È consigliabile reimpostare questa proprietà se il controllo ha un altro ruolo. Se, ad esempio, si usa un controllo **PictureBox** come un **grafico**, è possibile fare in modo che il ruolo venga segnalato come **Chart**anziché come **PictureBox**. È anche consigliabile specificare questa proprietà per eventuali controlli personalizzati sviluppati. La proprietà può essere impostata nella finestra Proprietà o nel codice, come illustrato di seguito:  
  
```vb
PictureBox1.AccessibleRole = AccessibleRole.Chart  
```

```csharp  
PictureBox1.AccessibleRole = AccessibleRole.Chart;  
```

```cpp  
pictureBox1->AccessibleRole = AccessibleRole::Chart;  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.AccessibleObject>
- <xref:System.Windows.Forms.Control.AccessibilityObject%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDescription%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleName%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleRole%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.AccessibleRole>
