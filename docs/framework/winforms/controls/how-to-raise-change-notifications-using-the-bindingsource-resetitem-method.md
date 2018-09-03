---
title: 'Procedura: generare notifiche di modifica utilizzando il metodo ResetItem di BindingSource'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- change notifications [Windows Forms], raising
- data binding [Windows Forms], change notifications
- BindingSource component [Windows Forms], raising change notifications with
- data sources [Windows Forms], detecting changes
- change notifications
ms.assetid: ab8b4096-37ff-4e30-aabc-de79a2f2e972
ms.openlocfilehash: cd2a15d5c3cbdf15f055196e63548a1240202479
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43488105"
---
# <a name="how-to-raise-change-notifications-using-the-bindingsource-resetitem-method"></a><span data-ttu-id="ff976-102">Procedura: generare notifiche di modifica utilizzando il metodo ResetItem di BindingSource</span><span class="sxs-lookup"><span data-stu-id="ff976-102">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>
<span data-ttu-id="ff976-103">Alcune origini dati dei controlli non generano notifiche di modifica quando si verificano modifiche, aggiunte o eliminazioni di elementi.</span><span class="sxs-lookup"><span data-stu-id="ff976-103">Some data sources for your controls do not raise change notifications when items are changed, added, or deleted.</span></span> <span data-ttu-id="ff976-104">Il componente <xref:System.Windows.Forms.BindingSource> consente di eseguire l'associazione a tali origini dati e di generare una notifica di modifica dal codice.</span><span class="sxs-lookup"><span data-stu-id="ff976-104">With the <xref:System.Windows.Forms.BindingSource> component, you can bind to such data sources and raise a change notification from your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff976-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="ff976-105">Example</span></span>  
 <span data-ttu-id="ff976-106">Questo form illustra l'uso di un componente <xref:System.Windows.Forms.BindingSource> per associare un elenco a un controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="ff976-106">This form demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind a list to a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="ff976-107">Poiché l'elenco non genera notifiche di modifica, quando un elemento dell'elenco subisce una modifica viene chiamato il metodo <xref:System.Windows.Forms.BindingSource.ResetItem%2A> dell'elemento <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="ff976-107">The list does not raise change notifications, so the <xref:System.Windows.Forms.BindingSource.ResetItem%2A> method on the <xref:System.Windows.Forms.BindingSource> is called when an item in the list is changed.</span></span> <span data-ttu-id="ff976-108">.</span><span class="sxs-lookup"><span data-stu-id="ff976-108">.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetItem#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetItem#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetItem#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ff976-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="ff976-109">Compiling the Code</span></span>  
 <span data-ttu-id="ff976-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ff976-110">This example requires:</span></span>  
  
-   <span data-ttu-id="ff976-111">Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="ff976-111">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="ff976-112">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="ff976-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="ff976-113">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="ff976-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="ff976-114">Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Form completo tramite Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="ff976-114">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff976-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff976-115">See Also</span></span>  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="ff976-116">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="ff976-116">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="ff976-117">Procedura: Associare un controllo di Windows Form a un tipo</span><span class="sxs-lookup"><span data-stu-id="ff976-117">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
