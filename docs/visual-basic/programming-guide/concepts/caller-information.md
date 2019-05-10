---
title: Informazioni sul chiamante (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 15d556eb-4d0c-4497-98a3-7f60abb7d6a1
ms.openlocfilehash: d9dc542ee9b800cfe6342f868ff9c2b170a4beec
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64642357"
---
# <a name="caller-information-visual-basic"></a><span data-ttu-id="a3618-102">Informazioni sul chiamante (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a3618-102">Caller Information (Visual Basic)</span></span>
<span data-ttu-id="a3618-103">Gli attributi di informazioni sul chiamante consentono di ottenere informazioni sul chiamante di un metodo.</span><span class="sxs-lookup"><span data-stu-id="a3618-103">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="a3618-104">È possibile ottenere il percorso del file del codice sorgente, il numero di riga nel codice sorgente e il nome del chiamante.</span><span class="sxs-lookup"><span data-stu-id="a3618-104">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="a3618-105">Queste informazioni sono utili per la tracciatura, il debug e la creazione di strumenti diagnostici.</span><span class="sxs-lookup"><span data-stu-id="a3618-105">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>  
  
 <span data-ttu-id="a3618-106">Per ottenere queste informazioni, utilizzare gli attributi applicati ai parametri facoltativi, a ognuno dei quali è associato un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="a3618-106">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="a3618-107">Nella tabella seguente sono elencati gli attributi di informazioni sul chiamante definiti nello spazio dei nomi <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="a3618-107">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace:</span></span>  
  
|<span data-ttu-id="a3618-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="a3618-108">Attribute</span></span>|<span data-ttu-id="a3618-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3618-109">Description</span></span>|<span data-ttu-id="a3618-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="a3618-110">Type</span></span>|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|<span data-ttu-id="a3618-111">Percorso completo del file di origine contenente il chiamante.</span><span class="sxs-lookup"><span data-stu-id="a3618-111">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="a3618-112">Si tratta del percorso del file al momento della compilazione.</span><span class="sxs-lookup"><span data-stu-id="a3618-112">This is the file path at compile time.</span></span>|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|<span data-ttu-id="a3618-113">Numero di riga nel file di origine in cui viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="a3618-113">Line number in the source file at which the method is called.</span></span>|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|<span data-ttu-id="a3618-114">Nome di una proprietà o di un metodo del chiamante.</span><span class="sxs-lookup"><span data-stu-id="a3618-114">Method or property name of the caller.</span></span> <span data-ttu-id="a3618-115">Vedere [Nomi dei membri](#MEMBERNAMES) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a3618-115">See [Member Names](#MEMBERNAMES) later in this topic.</span></span>|`String`|  
  
## <a name="example"></a><span data-ttu-id="a3618-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="a3618-116">Example</span></span>  
 <span data-ttu-id="a3618-117">Nell'esempio seguente viene illustrato come utilizzare gli attributi di informazioni sul chiamante.</span><span class="sxs-lookup"><span data-stu-id="a3618-117">The following example shows how to use Caller Info attributes.</span></span> <span data-ttu-id="a3618-118">Per ogni chiamata al metodo `TraceMessage`, le informazioni sul chiamante vengono sostituite come argomenti dei parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="a3618-118">On each call to the `TraceMessage` method, the caller information is substituted as arguments to the optional parameters.</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="a3618-119">Note</span><span class="sxs-lookup"><span data-stu-id="a3618-119">Remarks</span></span>  
 <span data-ttu-id="a3618-120">È sempre necessario specificare un valore esplicito per ciascun parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a3618-120">You must specify an explicit default value for each optional parameter.</span></span> <span data-ttu-id="a3618-121">Non è possibile applicare attributi di informazioni sul chiamante ai parametri non specificati come facoltativi.</span><span class="sxs-lookup"><span data-stu-id="a3618-121">You can't apply Caller Info attributes to parameters that aren't specified as optional.</span></span>  
  
 <span data-ttu-id="a3618-122">Gli attributi di informazioni sul chiamante non restituiscono un parametro facoltativo,</span><span class="sxs-lookup"><span data-stu-id="a3618-122">The Caller Info attributes don't make a parameter optional.</span></span> <span data-ttu-id="a3618-123">ma influiscono sul valore predefinito passato quando l'argomento è omesso.</span><span class="sxs-lookup"><span data-stu-id="a3618-123">Instead, they affect the default value that's passed in when the argument is omitted.</span></span>  
  
 <span data-ttu-id="a3618-124">I valori delle informazioni sul chiamante vengono generati come valori letterali in Intermediate Language (IL) in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a3618-124">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="a3618-125">A differenza dei risultati della proprietà <xref:System.Exception.StackTrace%2A> per le eccezioni, i risultati non sono interessati da offuscamento.</span><span class="sxs-lookup"><span data-stu-id="a3618-125">Unlike the results of the <xref:System.Exception.StackTrace%2A> property for exceptions, the results aren't affected by obfuscation.</span></span>  
  
 <span data-ttu-id="a3618-126">È possibile fornire esplicitamente gli argomenti facoltativi per esaminare o nascondere le informazioni sul chiamante.</span><span class="sxs-lookup"><span data-stu-id="a3618-126">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>  
  
### <a name="MEMBERNAMES"></a> <span data-ttu-id="a3618-127">Nomi dei membri</span><span class="sxs-lookup"><span data-stu-id="a3618-127">Member Names</span></span>  
 <span data-ttu-id="a3618-128">È possibile utilizzare l'attributo `CallerMemberName` per specificare il nome del membro come argomento `String` al metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="a3618-128">You can use the `CallerMemberName` attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="a3618-129">Usando questa tecnica, si evita il problema per cui il **refactoring di ridenominazione** non modifica i valori `String`.</span><span class="sxs-lookup"><span data-stu-id="a3618-129">By using this technique, you avoid the problem that **Rename Refactoring** doesn't change the `String` values.</span></span> <span data-ttu-id="a3618-130">Questo vantaggio è particolarmente utile per le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="a3618-130">This benefit is especially useful for the following tasks:</span></span>  
  
- <span data-ttu-id="a3618-131">Utilizzo della tracciatura e delle routine di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="a3618-131">Using tracing and diagnostic routines.</span></span>  
  
- <span data-ttu-id="a3618-132">Implementazione dell'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged> durante l'associazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="a3618-132">Implementing the <xref:System.ComponentModel.INotifyPropertyChanged> interface when binding data.</span></span> <span data-ttu-id="a3618-133">Questa interfaccia consente alla proprietà di un oggetto di notificare a un controllo associato la modifica della proprietà stessa in modo che il controllo possa visualizzare le informazioni aggiornate.</span><span class="sxs-lookup"><span data-stu-id="a3618-133">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="a3618-134">Senza l'attributo `CallerMemberName`, è necessario specificare il nome della proprietà come valore letterale.</span><span class="sxs-lookup"><span data-stu-id="a3618-134">Without the `CallerMemberName` attribute, you must specify the property name as a literal.</span></span>  
  
 <span data-ttu-id="a3618-135">Nel grafico seguente vengono mostrati i nomi dei membri restituiti quando si utilizza l'attributo `CallerMemberName`.</span><span class="sxs-lookup"><span data-stu-id="a3618-135">The following chart shows the member names that are returned when you use the `CallerMemberName` attribute.</span></span>  
  
|<span data-ttu-id="a3618-136">Elemento in cui si verificano le chiamate</span><span class="sxs-lookup"><span data-stu-id="a3618-136">Calls occurs within</span></span>|<span data-ttu-id="a3618-137">Nome del membro restituito</span><span class="sxs-lookup"><span data-stu-id="a3618-137">Member name result</span></span>|  
|-------------------------|------------------------|  
|<span data-ttu-id="a3618-138">Metodo, proprietà o evento</span><span class="sxs-lookup"><span data-stu-id="a3618-138">Method, property, or event</span></span>|<span data-ttu-id="a3618-139">Nome del metodo, della proprietà o dell'evento da cui la chiamata ha avuto origine.</span><span class="sxs-lookup"><span data-stu-id="a3618-139">The name of the method, property, or event from which the call originated.</span></span>|  
|<span data-ttu-id="a3618-140">Costruttore</span><span class="sxs-lookup"><span data-stu-id="a3618-140">Constructor</span></span>|<span data-ttu-id="a3618-141">Stringa ".ctor"</span><span class="sxs-lookup"><span data-stu-id="a3618-141">The string ".ctor"</span></span>|  
|<span data-ttu-id="a3618-142">Costruttore statico</span><span class="sxs-lookup"><span data-stu-id="a3618-142">Static constructor</span></span>|<span data-ttu-id="a3618-143">Stringa ".cctor"</span><span class="sxs-lookup"><span data-stu-id="a3618-143">The string ".cctor"</span></span>|  
|<span data-ttu-id="a3618-144">Distruttore</span><span class="sxs-lookup"><span data-stu-id="a3618-144">Destructor</span></span>|<span data-ttu-id="a3618-145">Stringa "Finalize"</span><span class="sxs-lookup"><span data-stu-id="a3618-145">The string "Finalize"</span></span>|  
|<span data-ttu-id="a3618-146">Operatori o conversioni definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="a3618-146">User-defined operators or conversions</span></span>|<span data-ttu-id="a3618-147">Nome generato per il membro, ad esempio "op_Addition".</span><span class="sxs-lookup"><span data-stu-id="a3618-147">The generated name for the member, for example, "op_Addition".</span></span>|  
|<span data-ttu-id="a3618-148">Costruttore dell'attributo</span><span class="sxs-lookup"><span data-stu-id="a3618-148">Attribute constructor</span></span>|<span data-ttu-id="a3618-149">Nome del membro a cui viene applicato l'attributo.</span><span class="sxs-lookup"><span data-stu-id="a3618-149">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="a3618-150">Se l'attributo è un qualsiasi elemento in un membro (ad esempio un parametro, un valore restituito o un parametro di tipo generico), il risultato è il nome del membro associato a tale elemento.</span><span class="sxs-lookup"><span data-stu-id="a3618-150">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|  
|<span data-ttu-id="a3618-151">Nessun membro contenitore (ad esempio a livello di assembly o attributi applicati a tipi)</span><span class="sxs-lookup"><span data-stu-id="a3618-151">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="a3618-152">Valore predefinito del parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a3618-152">The default value of the optional parameter.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a3618-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3618-153">See also</span></span>

- [<span data-ttu-id="a3618-154">Attributi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a3618-154">Attributes (Visual Basic)</span></span>](../../../visual-basic/language-reference/attributes.md)
- [<span data-ttu-id="a3618-155">Attributi comuni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a3618-155">Common Attributes (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md)
- [<span data-ttu-id="a3618-156">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="a3618-156">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- <span data-ttu-id="a3618-157">[Programming Concepts (Visual Basic)](../../../visual-basic/programming-guide/concepts/index.md) (Concetti di programmazione (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="a3618-157">[Programming Concepts (Visual Basic)](../../../visual-basic/programming-guide/concepts/index.md)</span></span>
