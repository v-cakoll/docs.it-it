---
title: Informazioni sul chiamante (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
ms.assetid: 15d556eb-4d0c-4497-98a3-7f60abb7d6a1
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d9a028474a3bb7ae020f466d4dfe51608c43ab07
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="caller-information-visual-basic"></a><span data-ttu-id="79be0-102">Informazioni sul chiamante (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79be0-102">Caller Information (Visual Basic)</span></span>
<span data-ttu-id="79be0-103">Gli attributi di informazioni sul chiamante consentono di ottenere informazioni sul chiamante di un metodo.</span><span class="sxs-lookup"><span data-stu-id="79be0-103">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="79be0-104">È possibile ottenere il percorso del file del codice sorgente, il numero di riga nel codice sorgente e il nome del chiamante.</span><span class="sxs-lookup"><span data-stu-id="79be0-104">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="79be0-105">Queste informazioni sono utili per la tracciatura, il debug e la creazione di strumenti diagnostici.</span><span class="sxs-lookup"><span data-stu-id="79be0-105">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>  
  
 <span data-ttu-id="79be0-106">Per ottenere queste informazioni, utilizzare gli attributi applicati ai parametri facoltativi, a ognuno dei quali è associato un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="79be0-106">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="79be0-107">Nella tabella seguente vengono elencati gli attributi di informazioni sul chiamante definiti nel <xref:System.Runtime.CompilerServices?displayProperty=fullName>dello spazio dei nomi:</xref:System.Runtime.CompilerServices?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="79be0-107">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=fullName> namespace:</span></span>  
  
|<span data-ttu-id="79be0-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="79be0-108">Attribute</span></span>|<span data-ttu-id="79be0-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="79be0-109">Description</span></span>|<span data-ttu-id="79be0-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="79be0-110">Type</span></span>|  
|---|---|---|  
|<span data-ttu-id="79be0-111"><xref:System.Runtime.CompilerServices.CallerFilePathAttribute></xref:System.Runtime.CompilerServices.CallerFilePathAttribute></span><span class="sxs-lookup"><span data-stu-id="79be0-111"><xref:System.Runtime.CompilerServices.CallerFilePathAttribute></span></span>|<span data-ttu-id="79be0-112">Percorso completo del file di origine contenente il chiamante.</span><span class="sxs-lookup"><span data-stu-id="79be0-112">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="79be0-113">Si tratta del percorso del file al momento della compilazione.</span><span class="sxs-lookup"><span data-stu-id="79be0-113">This is the file path at compile time.</span></span>|`String`|  
|<span data-ttu-id="79be0-114"><xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></span><span class="sxs-lookup"><span data-stu-id="79be0-114"><xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></span></span>|<span data-ttu-id="79be0-115">Numero di riga nel file di origine in cui viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="79be0-115">Line number in the source file at which the method is called.</span></span>|`Integer`|  
|<span data-ttu-id="79be0-116"><xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></span><span class="sxs-lookup"><span data-stu-id="79be0-116"><xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></span></span>|<span data-ttu-id="79be0-117">Nome di una proprietà o di un metodo del chiamante.</span><span class="sxs-lookup"><span data-stu-id="79be0-117">Method or property name of the caller.</span></span> <span data-ttu-id="79be0-118">Vedere [i nomi dei membri](#MEMBERNAMES) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="79be0-118">See [Member Names](#MEMBERNAMES) later in this topic.</span></span>|`String`|  
  
## <a name="example"></a><span data-ttu-id="79be0-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="79be0-119">Example</span></span>  
 <span data-ttu-id="79be0-120">Nell'esempio seguente viene illustrato come utilizzare gli attributi di informazioni sul chiamante.</span><span class="sxs-lookup"><span data-stu-id="79be0-120">The following example shows how to use Caller Info attributes.</span></span> <span data-ttu-id="79be0-121">Per ogni chiamata al metodo `TraceMessage`, le informazioni sul chiamante vengono sostituite come argomenti dei parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="79be0-121">On each call to the `TraceMessage` method, the caller information is substituted as arguments to the optional parameters.</span></span>  
  
```vb  
Private Sub DoProcessing()  
    TraceMessage("Something happened.")  
End Sub  
  
Public Sub TraceMessage(message As String,  
        <System.Runtime.CompilerServices.CallerMemberName> Optional memberName As String = Nothing,  
        <System.Runtime.CompilerServices.CallerFilePath> Optional sourcefilePath As String = Nothing,  
        <System.Runtime.CompilerServices.CallerLineNumber()> Optional sourceLineNumber As Integer = 0)  
  
    System.Diagnostics.Trace.WriteLine("message: " & message)  
    System.Diagnostics.Trace.WriteLine("member name: " & memberName)  
    System.Diagnostics.Trace.WriteLine("source file path: " & sourcefilePath)  
    System.Diagnostics.Trace.WriteLine("source line number: " & sourceLineNumber)  
End Sub  
  
' Sample output:  
'   message: Something happened.  
'   member name: DoProcessing  
'   source file path: C:\Users\username\Documents\Visual Studio 2012\Projects\CallerInfoVB\CallerInfoVB\Form1.vb  
'   source line number: 15  
```  
  
## <a name="remarks"></a><span data-ttu-id="79be0-122">Note</span><span class="sxs-lookup"><span data-stu-id="79be0-122">Remarks</span></span>  
 <span data-ttu-id="79be0-123">È sempre necessario specificare un valore esplicito per ciascun parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="79be0-123">You must specify an explicit default value for each optional parameter.</span></span> <span data-ttu-id="79be0-124">Non è possibile applicare attributi di informazioni sul chiamante ai parametri non specificati come facoltativi.</span><span class="sxs-lookup"><span data-stu-id="79be0-124">You can't apply Caller Info attributes to parameters that aren't specified as optional.</span></span>  
  
 <span data-ttu-id="79be0-125">Gli attributi di informazioni sul chiamante non restituiscono un parametro facoltativo,</span><span class="sxs-lookup"><span data-stu-id="79be0-125">The Caller Info attributes don't make a parameter optional.</span></span> <span data-ttu-id="79be0-126">ma influiscono sul valore predefinito passato quando l'argomento è omesso.</span><span class="sxs-lookup"><span data-stu-id="79be0-126">Instead, they affect the default value that's passed in when the argument is omitted.</span></span>  
  
 <span data-ttu-id="79be0-127">I valori delle informazioni sul chiamante vengono generati come valori letterali in Intermediate Language (IL) in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="79be0-127">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="79be0-128">A differenza dei risultati della <xref:System.Exception.StackTrace%2A>proprietà per le eccezioni, i risultati non sono interessati da offuscamento.</xref:System.Exception.StackTrace%2A></span><span class="sxs-lookup"><span data-stu-id="79be0-128">Unlike the results of the <xref:System.Exception.StackTrace%2A> property for exceptions, the results aren't affected by obfuscation.</span></span>  
  
 <span data-ttu-id="79be0-129">È possibile fornire esplicitamente gli argomenti facoltativi per esaminare o nascondere le informazioni sul chiamante.</span><span class="sxs-lookup"><span data-stu-id="79be0-129">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>  
  
###  <span data-ttu-id="79be0-130"><a name="MEMBERNAMES"></a>Nomi dei membri</span><span class="sxs-lookup"><span data-stu-id="79be0-130"><a name="MEMBERNAMES"></a> Member Names</span></span>  
 <span data-ttu-id="79be0-131">È possibile utilizzare l'attributo `CallerMemberName` per specificare il nome del membro come argomento `String` al metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="79be0-131">You can use the `CallerMemberName` attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="79be0-132">Utilizzando questa tecnica, si evita il problema che **Refactoring di ridenominazione** non modifica il `String` valori.</span><span class="sxs-lookup"><span data-stu-id="79be0-132">By using this technique, you avoid the problem that **Rename Refactoring** doesn't change the `String` values.</span></span> <span data-ttu-id="79be0-133">Questo vantaggio è particolarmente utile per le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="79be0-133">This benefit is especially useful for the following tasks:</span></span>  
  
-   <span data-ttu-id="79be0-134">Utilizzo della tracciatura e delle routine di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="79be0-134">Using tracing and diagnostic routines.</span></span>  
  
-   <span data-ttu-id="79be0-135">Implementazione di <xref:System.ComponentModel.INotifyPropertyChanged>durante l'associazione di dati.</xref:System.ComponentModel.INotifyPropertyChanged></span><span class="sxs-lookup"><span data-stu-id="79be0-135">Implementing the <xref:System.ComponentModel.INotifyPropertyChanged> interface when binding data.</span></span> <span data-ttu-id="79be0-136">Questa interfaccia consente alla proprietà di un oggetto di notificare a un controllo associato la modifica della proprietà stessa in modo che il controllo possa visualizzare le informazioni aggiornate.</span><span class="sxs-lookup"><span data-stu-id="79be0-136">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="79be0-137">Senza l'attributo `CallerMemberName`, è necessario specificare il nome della proprietà come valore letterale.</span><span class="sxs-lookup"><span data-stu-id="79be0-137">Without the `CallerMemberName` attribute, you must specify the property name as a literal.</span></span>  
  
 <span data-ttu-id="79be0-138">Nel grafico seguente vengono mostrati i nomi dei membri restituiti quando si utilizza l'attributo `CallerMemberName`.</span><span class="sxs-lookup"><span data-stu-id="79be0-138">The following chart shows the member names that are returned when you use the `CallerMemberName` attribute.</span></span>  
  
|<span data-ttu-id="79be0-139">Elemento in cui si verificano le chiamate</span><span class="sxs-lookup"><span data-stu-id="79be0-139">Calls occurs within</span></span>|<span data-ttu-id="79be0-140">Nome del membro restituito</span><span class="sxs-lookup"><span data-stu-id="79be0-140">Member name result</span></span>|  
|-------------------------|------------------------|  
|<span data-ttu-id="79be0-141">Metodo, proprietà o evento</span><span class="sxs-lookup"><span data-stu-id="79be0-141">Method, property, or event</span></span>|<span data-ttu-id="79be0-142">Nome del metodo, della proprietà o dell'evento da cui la chiamata ha avuto origine.</span><span class="sxs-lookup"><span data-stu-id="79be0-142">The name of the method, property, or event from which the call originated.</span></span>|  
|<span data-ttu-id="79be0-143">Costruttore</span><span class="sxs-lookup"><span data-stu-id="79be0-143">Constructor</span></span>|<span data-ttu-id="79be0-144">Stringa ".ctor"</span><span class="sxs-lookup"><span data-stu-id="79be0-144">The string ".ctor"</span></span>|  
|<span data-ttu-id="79be0-145">Costruttore statico</span><span class="sxs-lookup"><span data-stu-id="79be0-145">Static constructor</span></span>|<span data-ttu-id="79be0-146">Stringa ".cctor"</span><span class="sxs-lookup"><span data-stu-id="79be0-146">The string ".cctor"</span></span>|  
|<span data-ttu-id="79be0-147">Distruttore</span><span class="sxs-lookup"><span data-stu-id="79be0-147">Destructor</span></span>|<span data-ttu-id="79be0-148">Stringa "Finalize"</span><span class="sxs-lookup"><span data-stu-id="79be0-148">The string "Finalize"</span></span>|  
|<span data-ttu-id="79be0-149">Operatori o conversioni definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="79be0-149">User-defined operators or conversions</span></span>|<span data-ttu-id="79be0-150">Nome generato per il membro, ad esempio "op_Addition".</span><span class="sxs-lookup"><span data-stu-id="79be0-150">The generated name for the member, for example, "op_Addition".</span></span>|  
|<span data-ttu-id="79be0-151">Costruttore dell'attributo</span><span class="sxs-lookup"><span data-stu-id="79be0-151">Attribute constructor</span></span>|<span data-ttu-id="79be0-152">Nome del membro a cui viene applicato l'attributo.</span><span class="sxs-lookup"><span data-stu-id="79be0-152">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="79be0-153">Se l'attributo è un qualsiasi elemento in un membro (ad esempio un parametro, un valore restituito o un parametro di tipo generico), il risultato è il nome del membro associato a tale elemento.</span><span class="sxs-lookup"><span data-stu-id="79be0-153">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|  
|<span data-ttu-id="79be0-154">Nessun membro contenitore (ad esempio a livello di assembly o attributi applicati a tipi)</span><span class="sxs-lookup"><span data-stu-id="79be0-154">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="79be0-155">Valore predefinito del parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="79be0-155">The default value of the optional parameter.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="79be0-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79be0-156">See Also</span></span>  
 <span data-ttu-id="79be0-157">[Attributi (Visual Basic)](../../../visual-basic/language-reference/attributes.md) </span><span class="sxs-lookup"><span data-stu-id="79be0-157">[Attributes (Visual Basic)](../../../visual-basic/language-reference/attributes.md) </span></span>  
<span data-ttu-id="79be0-158"> [Attributi comuni (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="79be0-158"> [Common Attributes (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md) </span></span>  
<span data-ttu-id="79be0-159"> [Parametri facoltativi](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="79be0-159"> [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md) </span></span>  
<span data-ttu-id="79be0-160"> [Concetti di programmazione (Visual Basic)](../../../visual-basic/programming-guide/concepts/index.md)</span><span class="sxs-lookup"><span data-stu-id="79be0-160"> [Programming Concepts (Visual Basic)](../../../visual-basic/programming-guide/concepts/index.md)</span></span>
