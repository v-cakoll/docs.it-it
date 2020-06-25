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
# <a name="how-to-display-time-with-the-datetimepicker-control"></a><span data-ttu-id="74abe-103">Procedura: visualizzare l'ora con il controllo DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="74abe-103">How to: Display Time with the DateTimePicker Control</span></span>
<span data-ttu-id="74abe-104">Se si vuole consentire agli utenti di selezionare una data e un'ora nell'applicazione e di visualizzare tali informazioni nel formato specificato, è possibile usare il controllo <xref:System.Windows.Forms.DateTimePicker>.</span><span class="sxs-lookup"><span data-stu-id="74abe-104">If you want your application to enable users to select a date and time, and to display that date and time in the specified format, use the <xref:System.Windows.Forms.DateTimePicker> control.</span></span> <span data-ttu-id="74abe-105">La procedura seguente illustra come usare il controllo <xref:System.Windows.Forms.DateTimePicker> per visualizzare l'ora.</span><span class="sxs-lookup"><span data-stu-id="74abe-105">The following procedure shows how to use the <xref:System.Windows.Forms.DateTimePicker> control to display the time.</span></span>  
  
### <a name="to-display-the-time-with-the-datetimepicker-control"></a><span data-ttu-id="74abe-106">Per visualizzare l'ora con il controllo DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="74abe-106">To display the time with the DateTimePicker control</span></span>  
  
1. <span data-ttu-id="74abe-107">Impostare la proprietà <xref:System.Windows.Forms.DateTimePicker.Format%2A> su <xref:System.Windows.Forms.DateTimePickerFormat.Time></span><span class="sxs-lookup"><span data-stu-id="74abe-107">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to <xref:System.Windows.Forms.DateTimePickerFormat.Time></span></span>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#2)]  
  
2. <span data-ttu-id="74abe-108">Impostare la proprietà <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> per <xref:System.Windows.Forms.DateTimePicker> su `true`.</span><span class="sxs-lookup"><span data-stu-id="74abe-108">Set the <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> property for the <xref:System.Windows.Forms.DateTimePicker> to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="74abe-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="74abe-109">Example</span></span>  
 <span data-ttu-id="74abe-110">Nell'esempio di codice seguente viene illustrato come creare un controllo <xref:System.Windows.Forms.DateTimePicker> che consente solo la scelta dell'ora.</span><span class="sxs-lookup"><span data-stu-id="74abe-110">The following code sample shows how to create a <xref:System.Windows.Forms.DateTimePicker> that enables users to choose a time only.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="74abe-111">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="74abe-111">Compiling the Code</span></span>  
 <span data-ttu-id="74abe-112">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="74abe-112">This example requires:</span></span>  
  
- <span data-ttu-id="74abe-113">Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="74abe-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74abe-114">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="74abe-114">See also</span></span>

- [<span data-ttu-id="74abe-115">Controllo DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="74abe-115">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
