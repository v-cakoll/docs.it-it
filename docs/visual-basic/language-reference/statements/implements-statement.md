---
title: Istruzione Implements (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: 805813506b957afb326c71ee4bbb15837726e4e5
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2018
ms.locfileid: "42907996"
---
# <a name="implements-statement"></a><span data-ttu-id="1eacf-102">Istruzione Implements</span><span class="sxs-lookup"><span data-stu-id="1eacf-102">Implements Statement</span></span>
<span data-ttu-id="1eacf-103">Specifica uno o più interfacce, o i membri di interfaccia, che devono essere implementati nella classe o definizione della struttura in cui è presente.</span><span class="sxs-lookup"><span data-stu-id="1eacf-103">Specifies one or more interfaces, or interface members, that must be implemented in the class or structure definition in which it appears.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1eacf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1eacf-104">Syntax</span></span>  
  
```  
Implements interfacename [, ...]  
-or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="1eacf-105">Parti</span><span class="sxs-lookup"><span data-stu-id="1eacf-105">Parts</span></span>  
 `interfacename`  
 <span data-ttu-id="1eacf-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1eacf-106">Required.</span></span> <span data-ttu-id="1eacf-107">Interfaccia la cui proprietà, procedure e gli eventi devono essere implementati dai membri corrispondenti nella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="1eacf-107">An interface whose properties, procedures, and events are to be implemented by corresponding members in the class or structure.</span></span>  
  
 `interfacemember`  
 <span data-ttu-id="1eacf-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1eacf-108">Required.</span></span> <span data-ttu-id="1eacf-109">Il membro di interfaccia implementato.</span><span class="sxs-lookup"><span data-stu-id="1eacf-109">The member of an interface that is being implemented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1eacf-110">Note</span><span class="sxs-lookup"><span data-stu-id="1eacf-110">Remarks</span></span>  
 <span data-ttu-id="1eacf-111">Un'interfaccia è una raccolta di prototipi che rappresentano i membri (proprietà, routine ed eventi) in essa contenuti.</span><span class="sxs-lookup"><span data-stu-id="1eacf-111">An interface is a collection of prototypes representing the members (properties, procedures, and events) the interface encapsulates.</span></span> <span data-ttu-id="1eacf-112">Le interfacce contengono solo le dichiarazioni per i membri. le classi e strutture di implementano questi membri.</span><span class="sxs-lookup"><span data-stu-id="1eacf-112">Interfaces contain only the declarations for members; classes and structures implement these members.</span></span> <span data-ttu-id="1eacf-113">Per altre informazioni, vedere [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="1eacf-113">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="1eacf-114">Il `Implements` istruzione deve seguire immediatamente la `Class` o `Structure` istruzione.</span><span class="sxs-lookup"><span data-stu-id="1eacf-114">The `Implements` statement must immediately follow the `Class` or `Structure` statement.</span></span>  
  
 <span data-ttu-id="1eacf-115">Quando si implementa un'interfaccia, è necessario implementare tutti i membri dichiarati nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="1eacf-115">When you implement an interface, you must implement all the members declared in the interface.</span></span> <span data-ttu-id="1eacf-116">Omissione di un membro viene considerato un errore di sintassi.</span><span class="sxs-lookup"><span data-stu-id="1eacf-116">Omitting any member is considered to be a syntax error.</span></span> <span data-ttu-id="1eacf-117">Per implementare un singolo membro, si specifica la [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) parola chiave (che si distinguono dal `Implements` istruzione) quando si dichiara il membro nella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="1eacf-117">To implement an individual member, you specify the [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) keyword (which is separate from the `Implements` statement) when you declare the member in the class or structure.</span></span> <span data-ttu-id="1eacf-118">Per altre informazioni, vedere [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="1eacf-118">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="1eacf-119">Le classi possono utilizzare [privato](../../../visual-basic/language-reference/modifiers/private.md) implementazioni di proprietà e routine, ma questi membri sono accessibili solo tramite il casting di un'istanza della classe di implementazione in una variabile dichiarata di tipo dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="1eacf-119">Classes can use [Private](../../../visual-basic/language-reference/modifiers/private.md) implementations of properties and procedures, but these members are accessible only by casting an instance of the implementing class into a variable declared to be of the type of the interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1eacf-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="1eacf-120">Example</span></span>  
 <span data-ttu-id="1eacf-121">Nell'esempio seguente viene illustrato come utilizzare il `Implements` istruzione per implementare i membri di un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="1eacf-121">The following example shows how to use the `Implements` statement to implement members of an interface.</span></span> <span data-ttu-id="1eacf-122">Definisce un'interfaccia denominata `ICustomerInfo` con un evento, una proprietà e una procedura.</span><span class="sxs-lookup"><span data-stu-id="1eacf-122">It defines an interface named `ICustomerInfo` with an event, a property, and a procedure.</span></span> <span data-ttu-id="1eacf-123">La classe `customerInfo` implementa tutti i membri definiti nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="1eacf-123">The class `customerInfo` implements all the members defined in the interface.</span></span>  
  
 [!code-vb[VbVbalrStatements#33](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_1.vb)]  
  
 <span data-ttu-id="1eacf-124">Si noti che la classe `customerInfo` utilizza le `Implements` istruzione in una riga di codice sorgente separato per indicare che la classe implementa tutti i membri del `ICustomerInfo` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="1eacf-124">Note that the class `customerInfo` uses the `Implements` statement on a separate source code line to indicate that the class implements all the members of the `ICustomerInfo` interface.</span></span> <span data-ttu-id="1eacf-125">Ogni membro nella classe Usa quindi il `Implements` (parola chiave) come parte della relativa dichiarazione di membro per indicare che l'implementazione di tale membro di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="1eacf-125">Then each member in the class uses the `Implements` keyword as part of its member declaration to indicate that it implements that interface member.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1eacf-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="1eacf-126">Example</span></span>  
 <span data-ttu-id="1eacf-127">Le due procedure seguenti illustrano come è possibile usare l'interfaccia implementata nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="1eacf-127">The following two procedures show how you could use the interface implemented in the preceding example.</span></span> <span data-ttu-id="1eacf-128">Per testare l'implementazione, aggiungere queste procedure per il progetto e la chiamata di `testImplements` procedure.</span><span class="sxs-lookup"><span data-stu-id="1eacf-128">To test the implementation, add these procedures to your project and call the `testImplements` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#34](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1eacf-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1eacf-129">See Also</span></span>  
 [<span data-ttu-id="1eacf-130">Implements</span><span class="sxs-lookup"><span data-stu-id="1eacf-130">Implements</span></span>](../../../visual-basic/language-reference/statements/implements-clause.md)  
 [<span data-ttu-id="1eacf-131">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="1eacf-131">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="1eacf-132">Interfacce</span><span class="sxs-lookup"><span data-stu-id="1eacf-132">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
