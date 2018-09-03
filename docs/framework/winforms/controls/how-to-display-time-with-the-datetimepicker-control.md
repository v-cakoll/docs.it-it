---
title: "Procedura: visualizzare l'ora con il controllo DateTimePicker"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time [Windows Forms], displaying in DateTimePicker control
- examples [Windows Forms], DateTimePicker control
- DateTimePicker control [Windows Forms], displaying time
ms.assetid: 0c1c8b40-1b50-4301-a90c-39516775ccb1
ms.openlocfilehash: c65a1102ccb8b05602d813831745dbcefed8c17d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43484393"
---
# <a name="how-to-display-time-with-the-datetimepicker-control"></a><span data-ttu-id="ab8a2-102">Procedura: visualizzare l'ora con il controllo DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="ab8a2-102">How to: Display Time with the DateTimePicker Control</span></span>
<span data-ttu-id="ab8a2-103">Se si vuole consentire agli utenti di selezionare una data e un'ora nell'applicazione e di visualizzare tali informazioni nel formato specificato, è possibile usare il controllo <xref:System.Windows.Forms.DateTimePicker>.</span><span class="sxs-lookup"><span data-stu-id="ab8a2-103">If you want your application to enable users to select a date and time, and to display that date and time in the specified format, use the <xref:System.Windows.Forms.DateTimePicker> control.</span></span> <span data-ttu-id="ab8a2-104">La procedura seguente illustra come usare il controllo <xref:System.Windows.Forms.DateTimePicker> per visualizzare l'ora.</span><span class="sxs-lookup"><span data-stu-id="ab8a2-104">The following procedure shows how to use the <xref:System.Windows.Forms.DateTimePicker> control to display the time.</span></span>  
  
### <a name="to-display-the-time-with-the-datetimepicker-control"></a><span data-ttu-id="ab8a2-105">Per visualizzare l'ora con il controllo DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="ab8a2-105">To display the time with the DateTimePicker control</span></span>  
  
1.  <span data-ttu-id="ab8a2-106">Impostare la proprietà <xref:System.Windows.Forms.DateTimePicker.Format%2A> su <xref:System.Windows.Forms.DateTimePickerFormat.Time></span><span class="sxs-lookup"><span data-stu-id="ab8a2-106">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to <xref:System.Windows.Forms.DateTimePickerFormat.Time></span></span>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#2)]  
  
2.  <span data-ttu-id="ab8a2-107">Impostare la proprietà <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> per <xref:System.Windows.Forms.DateTimePicker> su `true`.</span><span class="sxs-lookup"><span data-stu-id="ab8a2-107">Set the <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> property for the <xref:System.Windows.Forms.DateTimePicker> to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="ab8a2-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="ab8a2-108">Example</span></span>  
 <span data-ttu-id="ab8a2-109">Nell'esempio di codice seguente viene illustrato come creare un controllo <xref:System.Windows.Forms.DateTimePicker> che consente solo la scelta dell'ora.</span><span class="sxs-lookup"><span data-stu-id="ab8a2-109">The following code sample shows how to create a <xref:System.Windows.Forms.DateTimePicker> that enables users to choose a time only.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ab8a2-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="ab8a2-110">Compiling the Code</span></span>  
 <span data-ttu-id="ab8a2-111">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab8a2-111">This example requires:</span></span>  
  
-   <span data-ttu-id="ab8a2-112">Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="ab8a2-112">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="ab8a2-113">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="ab8a2-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="ab8a2-114">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="ab8a2-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="ab8a2-115">Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Form completo tramite Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="ab8a2-115">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab8a2-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab8a2-116">See Also</span></span>  
 [<span data-ttu-id="ab8a2-117">Controllo DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="ab8a2-117">DateTimePicker Control</span></span>](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)
