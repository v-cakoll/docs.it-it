---
title: "Procedura: visualizzare l'ora con il controllo DateTimePicker"
description: Informazioni su come usare il controllo DateTimePicker Windows Forms per consentire agli utenti di selezionare una data e un'ora e di visualizzare la data e l'ora nel formato specificato.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time [Windows Forms], displaying in DateTimePicker control
- examples [Windows Forms], DateTimePicker control
- DateTimePicker control [Windows Forms], displaying time
ms.assetid: 0c1c8b40-1b50-4301-a90c-39516775ccb1
ms.openlocfilehash: ab584367a189d05e567bb57d386c6bf629201102
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325588"
---
# <a name="how-to-display-time-with-the-datetimepicker-control"></a>Procedura: visualizzare l'ora con il controllo DateTimePicker
Se si vuole consentire agli utenti di selezionare una data e un'ora nell'applicazione e di visualizzare tali informazioni nel formato specificato, è possibile usare il controllo <xref:System.Windows.Forms.DateTimePicker>. La procedura seguente illustra come usare il controllo <xref:System.Windows.Forms.DateTimePicker> per visualizzare l'ora.  
  
### <a name="to-display-the-time-with-the-datetimepicker-control"></a>Per visualizzare l'ora con il controllo DateTimePicker  
  
1. Impostare la proprietà <xref:System.Windows.Forms.DateTimePicker.Format%2A> su <xref:System.Windows.Forms.DateTimePickerFormat.Time>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#2)]  
  
2. Impostare la proprietà <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> per <xref:System.Windows.Forms.DateTimePicker> su `true`.  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#3)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrato come creare un controllo <xref:System.Windows.Forms.DateTimePicker> che consente solo la scelta dell'ora.  
  
 [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.  
  
## <a name="see-also"></a>Vedi anche

- [Controllo DateTimePicker](datetimepicker-control-windows-forms.md)
