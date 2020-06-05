---
title: Proprietà implementate automaticamente
ms.date: 07/20/2015
f1_keywords:
- vb.AutoProperty
- vb.AutoImplementedProperty
helpviewer_keywords:
- properties [Visual Basic], auto-implemented
- auto-implemented properties [Visual Basic]
ms.assetid: 5c669f0b-cf95-4b4e-ae84-9cc55212ca87
ms.openlocfilehash: d991a385e537c43daeb708e96e712acd92110379
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403382"
---
# <a name="auto-implemented-properties-visual-basic"></a><span data-ttu-id="8e3eb-102">Proprietà implementate automaticamente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e3eb-102">Auto-Implemented Properties (Visual Basic)</span></span>
<span data-ttu-id="8e3eb-103">Le *proprietà implementate automaticamente* consentono di specificare rapidamente una proprietà di una classe senza dover scrivere codice in `Get` e `Set` la proprietà.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-103">*Auto-implemented properties* enable you to quickly specify a property of a class without having to write code to `Get` and `Set` the property.</span></span> <span data-ttu-id="8e3eb-104">Quando si scrive il codice per una proprietà implementata automaticamente, il compilatore Visual Basic crea automaticamente un campo privato per archiviare la variabile della proprietà oltre a creare le routine `Get` e `Set` associate.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-104">When you write code for an auto-implemented property, the Visual Basic compiler automatically creates a private field to store the property variable in addition to creating the associated `Get` and `Set` procedures.</span></span>  
  
 <span data-ttu-id="8e3eb-105">Con le proprietà implementate automaticamente, una proprietà, incluso un valore predefinito, può essere dichiarata in una sola riga.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-105">With auto-implemented properties, a property, including a default value, can be declared in a single line.</span></span> <span data-ttu-id="8e3eb-106">L'esempio seguente illustra tre dichiarazioni di proprietà. </span><span class="sxs-lookup"><span data-stu-id="8e3eb-106">The following example shows three property declarations.</span></span>  
  
 [!code-vb[VbVbalrAutoImplementedProperties#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#1)]  
  
 <span data-ttu-id="8e3eb-107">Una proprietà implementata automaticamente equivale a una proprietà il cui valore viene archiviato in un campo privato.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-107">An auto-implemented property is equivalent to a property for which the property value is stored in a private field.</span></span> <span data-ttu-id="8e3eb-108">L'esempio di codice seguente illustra una proprietà implementata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-108">The following code example shows an auto-implemented property.</span></span>  
  
 [!code-vb[VbVbalrAutoImplementedProperties#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#5)]  
  
 <span data-ttu-id="8e3eb-109">L'esempio seguente illustra il codice equivalente per il precedente esempio di proprietà implementata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-109">The following code example shows the equivalent code for the previous auto-implemented property example.</span></span>  
  
 [!code-vb[VbVbalrAutoImplementedProperties#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#2)]  
  
 <span data-ttu-id="8e3eb-110">Il codice seguente illustra l'implementazione delle proprietà di sola lettura:</span><span class="sxs-lookup"><span data-stu-id="8e3eb-110">The following code show implementing readonly properties:</span></span>  
  
```vb  
Class Customer  
   Public ReadOnly Property Tags As New List(Of String)  
   Public ReadOnly Property Name As String = ""  
   Public ReadOnly Property File As String  
  
   Sub New(file As String)  
      Me.File = file  
   End Sub  
End Class  
```  
  
 <span data-ttu-id="8e3eb-111">È possibile assegnare alla proprietà con espressioni di inizializzazione, come illustrato nell'esempio, oppure nel costruttore del tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-111">You can assign to the property with initialization expressions as shown in the example, or you can assign to the properties in the containing type’s constructor.</span></span>  <span data-ttu-id="8e3eb-112">È possibile assegnare ai campi sottostanti delle proprietà di sola lettura in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-112">You can assign to the backing fields of readonly properties at any time.</span></span>  
  
## <a name="backing-field"></a><span data-ttu-id="8e3eb-113">Campo sottostante</span><span class="sxs-lookup"><span data-stu-id="8e3eb-113">Backing Field</span></span>  
 <span data-ttu-id="8e3eb-114">Quando si dichiara una proprietà implementata automaticamente, Visual Basic crea automaticamente un campo privato nascosto denominato *campo* sottostante per contenere il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-114">When you declare an auto-implemented property, Visual Basic automatically creates a hidden private field called the *backing field* to contain the property value.</span></span> <span data-ttu-id="8e3eb-115">Il nome del campo sottostante è il nome della proprietà implementata automaticamente preceduto da un carattere di sottolineatura (_).</span><span class="sxs-lookup"><span data-stu-id="8e3eb-115">The backing field name is the auto-implemented property name preceded by an underscore (_).</span></span> <span data-ttu-id="8e3eb-116">Ad esempio, se si dichiara una proprietà implementata automaticamente denominata `ID`, il campo sottostante viene denominato `_ID`.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-116">For example, if you declare an auto-implemented property named `ID`, the backing field is named `_ID`.</span></span> <span data-ttu-id="8e3eb-117">Se si include un membro della classe con il medesimo nome `_ID`, si produce un conflitto di denominazione e in Visual Basic viene segnalato un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-117">If you include a member of your class that is also named `_ID`, you produce a naming conflict and Visual Basic reports a compiler error.</span></span>  
  
 <span data-ttu-id="8e3eb-118">Il campo sottostante presenta inoltre le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="8e3eb-118">The backing field also has the following characteristics:</span></span>  
  
- <span data-ttu-id="8e3eb-119">Il modificatore di accesso per il campo sottostante è sempre `Private`, anche quando la proprietà stessa dispone di un livello di accesso diverso, ad esempio `Public`.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-119">The access modifier for the backing field is always `Private`, even when the property itself has a different access level, such as `Public`.</span></span>  
  
- <span data-ttu-id="8e3eb-120">Se la proprietà è contrassegnata come `Shared`, anche il campo sottostante è condiviso.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-120">If the property is marked as `Shared`, the backing field also is shared.</span></span>  
  
- <span data-ttu-id="8e3eb-121">Gli attributi specificati per la proprietà non si applicano al campo sottostante.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-121">Attributes specified for the property do not apply to the backing field.</span></span>  
  
- <span data-ttu-id="8e3eb-122">L'accesso al campo sottostante può essere eseguito dal codice all'interno della classe e dagli strumenti di debug, ad esempio la finestra Espressioni di controllo.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-122">The backing field can be accessed from code within the class and from debugging tools such as the Watch window.</span></span> <span data-ttu-id="8e3eb-123">Tuttavia, il campo sottostante non viene visualizzato in un elenco di completamento di parole di IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-123">However, the backing field does not show in an IntelliSense word completion list.</span></span>  
  
## <a name="initializing-an-auto-implemented-property"></a><span data-ttu-id="8e3eb-124">Inizializzazione di una proprietà implementata automaticamente</span><span class="sxs-lookup"><span data-stu-id="8e3eb-124">Initializing an Auto-Implemented Property</span></span>  
 <span data-ttu-id="8e3eb-125">Qualsiasi espressione utilizzabile per inizializzare un campo è valida per l'inizializzazione di una proprietà implementata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-125">Any expression that can be used to initialize a field is valid for initializing an auto-implemented property.</span></span> <span data-ttu-id="8e3eb-126">Quando si inizializza una proprietà implementata automaticamente, l'espressione viene valutata e passata alla routine `Set` per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-126">When you initialize an auto-implemented property, the expression is evaluated and passed to the `Set` procedure for the property.</span></span> <span data-ttu-id="8e3eb-127">Gli esempi di codice seguenti mostrano alcune proprietà implementate automaticamente che includono i valori iniziali.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-127">The following code examples show some auto-implemented properties that include initial values.</span></span>  
  
 [!code-vb[VbVbalrAutoImplementedProperties#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#3)]  
  
 <span data-ttu-id="8e3eb-128">Non è possibile inizializzare una proprietà implementata automaticamente che sia membro di un `Interface` o una che sia contrassegnata come `MustOverride`.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-128">You cannot initialize an auto-implemented property that is a member of an `Interface`, or one that is marked `MustOverride`.</span></span>  
  
 <span data-ttu-id="8e3eb-129">Quando si dichiara una proprietà implementata automaticamente come membro di una `Structure`, è possibile inizializzarla solo se è contrassegnata come `Shared`.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-129">When you declare an auto-implemented property as a member of a `Structure`, you can only initialize the auto-implemented property if it is marked as `Shared`.</span></span>  
  
 <span data-ttu-id="8e3eb-130">Quando si dichiara una proprietà implementata automaticamente come matrice, non è possibile specificare limiti di matrice espliciti.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-130">When you declare an auto-implemented property as an array, you cannot specify explicit array bounds.</span></span> <span data-ttu-id="8e3eb-131">Tuttavia, si può specificare un valore usando un inizializzatore di matrice, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-131">However, you can supply a value by using an array initializer, as shown in the following examples.</span></span>  
  
 [!code-vb[VbVbalrAutoImplementedProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrautoimplementedproperties/vb/module1.vb#4)]  
  
## <a name="property-definitions-that-require-standard-syntax"></a><span data-ttu-id="8e3eb-132">Definizioni di proprietà che richiedono la sintassi standard</span><span class="sxs-lookup"><span data-stu-id="8e3eb-132">Property Definitions That Require Standard Syntax</span></span>  
 <span data-ttu-id="8e3eb-133">Le proprietà implementate automaticamente sono semplici da usare e supportano molti scenari di programmazione.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-133">Auto-implemented properties are convenient and support many programming scenarios.</span></span> <span data-ttu-id="8e3eb-134">Tuttavia, esistono situazioni in cui non è possibile usare una proprietà implementata automaticamente e deve invece usare la sintassi di proprietà standard o *Expanded*.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-134">However, there are situations in which you cannot use an auto-implemented property and must instead use standard, or *expanded*, property syntax.</span></span>  
  
 <span data-ttu-id="8e3eb-135">È necessario usare la sintassi di definizione della proprietà espansa se si vuole eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8e3eb-135">You have to use expanded property-definition syntax if you want to do any one of the following:</span></span>  
  
- <span data-ttu-id="8e3eb-136">Aggiungere codice alla routine `Get` o `Set` di una proprietà, ad esempio il codice per convalidare i valori in ingresso nella routine `Set`.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-136">Add code to the `Get` or `Set` procedure of a property, such as code to validate incoming values in the `Set` procedure.</span></span> <span data-ttu-id="8e3eb-137">È possibile, ad esempio, verificare che una stringa che rappresenta un numero di telefono contenga il numero obbligatorio di numerali prima di impostare il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-137">For example, you might want to verify that a string that represents a telephone number contains the required number of numerals before setting the property value.</span></span>  
  
- <span data-ttu-id="8e3eb-138">Specificare un'accessibilità diversa per le routine `Get` e `Set`.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-138">Specify different accessibility for the `Get` and `Set` procedure.</span></span> <span data-ttu-id="8e3eb-139">Ad esempio, si può impostare la routine `Set` come `Private` e la routine `Get` come `Public`.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-139">For example, you might want to make the `Set` procedure `Private` and the `Get` procedure `Public`.</span></span>  
  
- <span data-ttu-id="8e3eb-140">Creare proprietà `WriteOnly`.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-140">Create properties that are `WriteOnly`.</span></span>  
  
- <span data-ttu-id="8e3eb-141">Usare proprietà con parametri (incluse le proprietà `Default`).</span><span class="sxs-lookup"><span data-stu-id="8e3eb-141">Use parameterized properties (including `Default` properties).</span></span> <span data-ttu-id="8e3eb-142">È necessario dichiarare una proprietà espansa per specificare un parametro per la proprietà o per specificare parametri aggiuntivi per la routine `Set`.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-142">You must declare an expanded property in order to specify a parameter for the property, or to specify additional parameters for the `Set` procedure.</span></span>  
  
- <span data-ttu-id="8e3eb-143">Inserire un attributo nel campo sottostante o modificare il livello di accesso del campo sottostante.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-143">Place an attribute on the backing field, or change the access level of the backing field.</span></span>  
  
- <span data-ttu-id="8e3eb-144">Fornire commenti XML per il campo sottostante.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-144">Provide XML comments for the backing field.</span></span>  
  
## <a name="expanding-an-auto-implemented-property"></a><span data-ttu-id="8e3eb-145">Espansione di una proprietà implementata automaticamente</span><span class="sxs-lookup"><span data-stu-id="8e3eb-145">Expanding an Auto-Implemented Property</span></span>  
 <span data-ttu-id="8e3eb-146">Se è necessario convertire una proprietà implementata automaticamente in una proprietà espansa contenente una routine `Get` o `Set`, l'editor di codice di Visual Basic può generare automaticamente le routine `Get` e `Set` e l'istruzione `End Property` per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-146">If you have to convert an auto-implemented property to an expanded property that contains a `Get` or `Set` procedure, the Visual Basic Code Editor can automatically generate the `Get` and `Set` procedures and `End Property` statement for the property.</span></span> <span data-ttu-id="8e3eb-147">Il codice viene generato se si inserisce il cursore su una riga vuota che segue l' `Property` istruzione, si digita un `G` (per `Get` ) o un `S` (per `Set` ) e si preme INVIO.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-147">The code is generated if you put the cursor on a blank line following the `Property` statement, type a `G` (for `Get`) or an `S` (for `Set`) and press ENTER.</span></span> <span data-ttu-id="8e3eb-148">L'editor di codice di Visual Basic genera automaticamente la routine `Get` o `Set` per le proprietà di sola lettura e di sola scrittura quando si preme INVIO alla fine di un'istruzione `Property`.</span><span class="sxs-lookup"><span data-stu-id="8e3eb-148">The Visual Basic Code Editor automatically generates the `Get` or `Set` procedure for read-only and write-only properties when you press ENTER at the end of a `Property` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e3eb-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e3eb-149">See also</span></span>

- [<span data-ttu-id="8e3eb-150">Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8e3eb-150">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="8e3eb-151">Procedura: dichiarare una proprietà con livelli di accesso misti</span><span class="sxs-lookup"><span data-stu-id="8e3eb-151">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="8e3eb-152">Property Statement</span><span class="sxs-lookup"><span data-stu-id="8e3eb-152">Property Statement</span></span>](../../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="8e3eb-153">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="8e3eb-153">ReadOnly</span></span>](../../../language-reference/modifiers/readonly.md)
- [<span data-ttu-id="8e3eb-154">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="8e3eb-154">WriteOnly</span></span>](../../../language-reference/modifiers/writeonly.md)
- [<span data-ttu-id="8e3eb-155">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="8e3eb-155">Objects and Classes</span></span>](../objects-and-classes/index.md)
