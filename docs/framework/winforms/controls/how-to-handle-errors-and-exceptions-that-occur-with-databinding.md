---
title: "Procedura: gestire gli errori e le eccezioni che si verificano con l'associazione dati"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- error handling [Windows Forms], examples
- data binding [Windows Forms], examples
- examples [Windows Forms], error handling
- error handling [Windows Forms], data binding
- data binding [Windows Forms], error handling
- BindingSource component [Windows Forms], handling errors and exceptions
ms.assetid: eddc5bad-9513-47df-ab28-f02d8dff7892
ms.openlocfilehash: d0bb41da69bf1cb87f052c11d3a7d1f1783320ad
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43532676"
---
# <a name="how-to-handle-errors-and-exceptions-that-occur-with-databinding"></a><span data-ttu-id="aaa73-102">Procedura: gestire gli errori e le eccezioni che si verificano con l'associazione dati</span><span class="sxs-lookup"><span data-stu-id="aaa73-102">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>
<span data-ttu-id="aaa73-103">Spesso si verificano eccezioni ed errori negli oggetti business sottostanti quando li si associa ai controlli.</span><span class="sxs-lookup"><span data-stu-id="aaa73-103">Oftentimes exceptions and errors occur on the underlying business objects when you bind them to controls.</span></span> <span data-ttu-id="aaa73-104">È possibile intercettare questi errori ed eccezioni e quindi eseguire il ripristino o passare le informazioni sull'errore all'utente gestendo l'evento <xref:System.Windows.Forms.Binding.BindingComplete> per un determinato componente <xref:System.Windows.Forms.Binding>, <xref:System.Windows.Forms.BindingSource> o <xref:System.Windows.Forms.CurrencyManager>.</span><span class="sxs-lookup"><span data-stu-id="aaa73-104">You can intercept these errors and exceptions and then either recover or pass the error information to the user by handling the <xref:System.Windows.Forms.Binding.BindingComplete> event for a particular <xref:System.Windows.Forms.Binding>, <xref:System.Windows.Forms.BindingSource>, or <xref:System.Windows.Forms.CurrencyManager> component.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aaa73-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="aaa73-105">Example</span></span>  
 <span data-ttu-id="aaa73-106">Questo esempio di codice illustra come gestire gli errori e le eccezioni che si verificano durante un'operazione di data binding.</span><span class="sxs-lookup"><span data-stu-id="aaa73-106">This code example demonstrates how to handle errors and exceptions that occur during a data-binding operation.</span></span> <span data-ttu-id="aaa73-107">Spiega come intercettare gli errori gestendo l'evento <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> dell'oggetto <xref:System.Windows.Forms.Binding>.</span><span class="sxs-lookup"><span data-stu-id="aaa73-107">It demonstrates how to intercept errors by handling the <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> event of the <xref:System.Windows.Forms.Binding> objects.</span></span> <span data-ttu-id="aaa73-108">Per intercettare errori ed eccezioni gestendo questo evento, è necessario abilitare la formattazione per il binding.</span><span class="sxs-lookup"><span data-stu-id="aaa73-108">In order to intercept errors and exceptions by handling this event, you must enable formatting for the binding.</span></span> <span data-ttu-id="aaa73-109">È possibile abilitare la formattazione quando il binding viene costruito o aggiunto alla raccolta di binding oppure impostando la proprietà <xref:System.Windows.Forms.Binding.FormattingEnabled%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="aaa73-109">You can enable formatting when the binding is constructed or added to the binding collection, or by setting the <xref:System.Windows.Forms.Binding.FormattingEnabled%2A> property to `true`.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CPP/form1.cpp#3)]
 [!code-csharp[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CS/form1.cs#3)]
 [!code-vb[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/VB/form1.vb#3)]  
  
 <span data-ttu-id="aaa73-110">Quando il codice è in esecuzione e viene immessa una stringa vuota come nome parte o un valore inferiore a 100 come codice, appare una finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="aaa73-110">When the code is running and an empty string is entered for the part name or a value less than 100 is entered for the part number, a message box appears.</span></span> <span data-ttu-id="aaa73-111">Si tratta di un risultato della gestione dell'evento <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> per questi binding di caselle di testo.</span><span class="sxs-lookup"><span data-stu-id="aaa73-111">This is a result of handling the <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> event for these textbox bindings.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="aaa73-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="aaa73-112">Compiling the Code</span></span>  
 <span data-ttu-id="aaa73-113">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="aaa73-113">This example requires:</span></span>  
  
-   <span data-ttu-id="aaa73-114">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="aaa73-114">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="aaa73-115">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="aaa73-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="aaa73-116">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="aaa73-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="aaa73-117">Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Form completo tramite Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="aaa73-117">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaa73-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aaa73-118">See Also</span></span>  
 <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.BindingSource.BindingComplete?displayProperty=nameWithType>  
 [<span data-ttu-id="aaa73-119">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="aaa73-119">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)
