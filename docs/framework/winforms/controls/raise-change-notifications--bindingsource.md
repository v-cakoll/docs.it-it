---
title: "Procedura: generare notifiche di modifica utilizzando un BindingSource e l'interfaccia INotifyPropertyChanged"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- change notifications [Windows Forms], raising
- BindingSource component [Windows Forms], and IPropertyChange
- data sources [Windows Forms], detecting changes
- examples [Windows Forms], BindingSource component
- change notifications
- INotifyPropertyChanged interface [Windows Forms], using with BindingSource
- BindingSource component [Windows Forms], examples
ms.assetid: 7fa2cf51-c09f-4375-adf0-e36c5617f099
ms.openlocfilehash: 039875473fe3bd1702ad43465edae2c73ffcadca
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "47234963"
---
# <a name="how-to-raise-change-notifications-using-a-bindingsource-and-the-inotifypropertychanged-interface"></a><span data-ttu-id="8ce6f-102">Procedura: generare notifiche di modifica utilizzando un BindingSource e l'interfaccia INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="8ce6f-102">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>
<span data-ttu-id="8ce6f-103">Il componente <xref:System.Windows.Forms.BindingSource> rileva automaticamente le modifiche in un'origine dati quando il tipo contenuto nell'origine dati implementa l'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged> e genera eventi <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> nel momento in cui il valore di una proprietà viene modificato.</span><span class="sxs-lookup"><span data-stu-id="8ce6f-103">The <xref:System.Windows.Forms.BindingSource> component will automatically detect changes in a data source when the type contained in the data source implements the <xref:System.ComponentModel.INotifyPropertyChanged> interface and raises <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> events when a property value is changed.</span></span> <span data-ttu-id="8ce6f-104">Si tratta di una caratteristica utile perché i controlli associati al componente <xref:System.Windows.Forms.BindingSource> verranno aggiornati automaticamente al variare dei valori dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="8ce6f-104">This is useful because controls bound to the <xref:System.Windows.Forms.BindingSource> will then automatically update as the data source values change.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ce6f-105">Se l'origine dati implementa <xref:System.ComponentModel.INotifyPropertyChanged> e devono essere eseguite operazioni asincrone, non devono essere apportate modifiche all'origine dati in un thread in background.</span><span class="sxs-lookup"><span data-stu-id="8ce6f-105">If your data source implements <xref:System.ComponentModel.INotifyPropertyChanged> and you are performing asynchronous operations, you should not make changes to the data source on a background thread.</span></span> <span data-ttu-id="8ce6f-106">In alternativa, è possibile leggere i dati in un thread in background e quindi unire i dati in un elenco nel thread dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="8ce6f-106">Instead, you should read the data on a background thread and merge the data into a list on the UI thread.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ce6f-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="8ce6f-107">Example</span></span>  
 <span data-ttu-id="8ce6f-108">Nell'esempio di codice riportato di seguito viene illustrata una semplice implementazione dell'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="8ce6f-108">The following code example demonstrates a simple implementation of the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="8ce6f-109">Viene inoltre descritto il modo in cui il componente <xref:System.Windows.Forms.BindingSource> passa automaticamente una modifica dell'origine dati a un controllo associato quando <xref:System.Windows.Forms.BindingSource> è associato a un elenco di tipo <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="8ce6f-109">It also shows how the <xref:System.Windows.Forms.BindingSource> automatically passes a data source change to a bound control when the <xref:System.Windows.Forms.BindingSource> is bound to a list of the <xref:System.ComponentModel.INotifyPropertyChanged> type.</span></span>  
  
 <span data-ttu-id="8ce6f-110">Se si usa l'attributo `CallerMemberName`, le chiamate al metodo `NotifyPropertyChanged` non devono specificare il nome della proprietà come argomento di tipo stringa.</span><span class="sxs-lookup"><span data-stu-id="8ce6f-110">If you use the `CallerMemberName` attribute, calls to the `NotifyPropertyChanged` method don't have to specify the property name as a string argument.</span></span> <span data-ttu-id="8ce6f-111">Per altre informazioni, vedere [informazioni sul chiamante](https://msdn.microsoft.com/library/9cb2b8c0-c4f6-44b8-9c90-38948455b373).</span><span class="sxs-lookup"><span data-stu-id="8ce6f-111">For more information, see [Caller Information](https://msdn.microsoft.com/library/9cb2b8c0-c4f6-44b8-9c90-38948455b373).</span></span>  
  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8ce6f-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="8ce6f-112">Compiling the Code</span></span>  
 <span data-ttu-id="8ce6f-113">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8ce6f-113">This example requires:</span></span>  
  
-   <span data-ttu-id="8ce6f-114">Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="8ce6f-114">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="8ce6f-115">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="8ce6f-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="8ce6f-116">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="8ce6f-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="8ce6f-117">Vedere anche [HYPERLINK "http://msdn.microsoft.com/library/Bb129228(v=vs.110)" procedura: compilare ed eseguire un Windows Form codice di esempio completo usando Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="8ce6f-117">Also see [HYPERLINK "http://msdn.microsoft.com/library/Bb129228(v=vs.110)" How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ce6f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ce6f-118">See Also</span></span>  
 <xref:System.ComponentModel.INotifyPropertyChanged>  
 [<span data-ttu-id="8ce6f-119">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="8ce6f-119">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="8ce6f-120">Procedura: generare notifiche di modifica utilizzando il metodo ResetItem di BindingSource</span><span class="sxs-lookup"><span data-stu-id="8ce6f-120">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>](../../../../docs/framework/winforms/controls/how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)
