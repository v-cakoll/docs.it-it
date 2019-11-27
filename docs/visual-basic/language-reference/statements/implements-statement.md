---
title: Istruzione Implements
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: e2e279b2c935dd082cbf832265a8ad09e6dffe9e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351144"
---
# <a name="implements-statement"></a><span data-ttu-id="6f036-102">Istruzione Implements</span><span class="sxs-lookup"><span data-stu-id="6f036-102">Implements Statement</span></span>
<span data-ttu-id="6f036-103">Specifica una o più interfacce o membri di interfaccia che devono essere implementati nella definizione della classe o della struttura in cui vengono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="6f036-103">Specifies one or more interfaces, or interface members, that must be implemented in the class or structure definition in which it appears.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f036-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6f036-104">Syntax</span></span>  
  
```vb  
Implements interfacename [, ...]  
' -or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="6f036-105">Parti</span><span class="sxs-lookup"><span data-stu-id="6f036-105">Parts</span></span>  
 `interfacename`  
 <span data-ttu-id="6f036-106">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="6f036-106">Required.</span></span> <span data-ttu-id="6f036-107">Interfaccia le cui proprietà, routine ed eventi devono essere implementati dai membri corrispondenti nella classe o nella struttura.</span><span class="sxs-lookup"><span data-stu-id="6f036-107">An interface whose properties, procedures, and events are to be implemented by corresponding members in the class or structure.</span></span>  
  
 `interfacemember`  
 <span data-ttu-id="6f036-108">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="6f036-108">Required.</span></span> <span data-ttu-id="6f036-109">Membro di un'interfaccia implementata.</span><span class="sxs-lookup"><span data-stu-id="6f036-109">The member of an interface that is being implemented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f036-110">Note</span><span class="sxs-lookup"><span data-stu-id="6f036-110">Remarks</span></span>  
 <span data-ttu-id="6f036-111">Un'interfaccia è una raccolta di prototipi che rappresentano i membri (proprietà, routine ed eventi) che l'interfaccia incapsula.</span><span class="sxs-lookup"><span data-stu-id="6f036-111">An interface is a collection of prototypes representing the members (properties, procedures, and events) the interface encapsulates.</span></span> <span data-ttu-id="6f036-112">Le interfacce contengono solo le dichiarazioni per i membri; le classi e le strutture implementano questi membri.</span><span class="sxs-lookup"><span data-stu-id="6f036-112">Interfaces contain only the declarations for members; classes and structures implement these members.</span></span> <span data-ttu-id="6f036-113">Per altre informazioni, vedere [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="6f036-113">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="6f036-114">L'istruzione `Implements` deve seguire immediatamente l'istruzione `Class` o `Structure`.</span><span class="sxs-lookup"><span data-stu-id="6f036-114">The `Implements` statement must immediately follow the `Class` or `Structure` statement.</span></span>  
  
 <span data-ttu-id="6f036-115">Quando si implementa un'interfaccia, è necessario implementare tutti i membri dichiarati nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="6f036-115">When you implement an interface, you must implement all the members declared in the interface.</span></span> <span data-ttu-id="6f036-116">L'omissione di qualsiasi membro viene considerato un errore di sintassi.</span><span class="sxs-lookup"><span data-stu-id="6f036-116">Omitting any member is considered to be a syntax error.</span></span> <span data-ttu-id="6f036-117">Per implementare un singolo membro, è necessario specificare la parola chiave [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) (che è separata dall'istruzione `Implements`) quando si dichiara il membro nella classe o nella struttura.</span><span class="sxs-lookup"><span data-stu-id="6f036-117">To implement an individual member, you specify the [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) keyword (which is separate from the `Implements` statement) when you declare the member in the class or structure.</span></span> <span data-ttu-id="6f036-118">Per altre informazioni, vedere [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="6f036-118">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="6f036-119">Le classi possono usare implementazioni [private](../../../visual-basic/language-reference/modifiers/private.md) di proprietà e procedure, ma questi membri sono accessibili solo eseguendo il cast di un'istanza della classe di implementazione in una variabile dichiarata come tipo dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="6f036-119">Classes can use [Private](../../../visual-basic/language-reference/modifiers/private.md) implementations of properties and procedures, but these members are accessible only by casting an instance of the implementing class into a variable declared to be of the type of the interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f036-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="6f036-120">Example</span></span>  
 <span data-ttu-id="6f036-121">Nell'esempio seguente viene illustrato come utilizzare l'istruzione `Implements` per implementare i membri di un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="6f036-121">The following example shows how to use the `Implements` statement to implement members of an interface.</span></span> <span data-ttu-id="6f036-122">Definisce un'interfaccia denominata `ICustomerInfo` con un evento, una proprietà e una routine.</span><span class="sxs-lookup"><span data-stu-id="6f036-122">It defines an interface named `ICustomerInfo` with an event, a property, and a procedure.</span></span> <span data-ttu-id="6f036-123">La classe `customerInfo` implementa tutti i membri definiti nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="6f036-123">The class `customerInfo` implements all the members defined in the interface.</span></span>  
  
 [!code-vb[VbVbalrStatements#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#33)]  
  
 <span data-ttu-id="6f036-124">Si noti che la classe `customerInfo` usa l'istruzione `Implements` su una riga di codice sorgente separata per indicare che la classe implementa tutti i membri dell'interfaccia `ICustomerInfo`.</span><span class="sxs-lookup"><span data-stu-id="6f036-124">Note that the class `customerInfo` uses the `Implements` statement on a separate source code line to indicate that the class implements all the members of the `ICustomerInfo` interface.</span></span> <span data-ttu-id="6f036-125">Ogni membro della classe usa quindi la parola chiave `Implements` come parte della dichiarazione del membro per indicare che implementa il membro di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="6f036-125">Then each member in the class uses the `Implements` keyword as part of its member declaration to indicate that it implements that interface member.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f036-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="6f036-126">Example</span></span>  
 <span data-ttu-id="6f036-127">Le due procedure seguenti illustrano come usare l'interfaccia implementata nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="6f036-127">The following two procedures show how you could use the interface implemented in the preceding example.</span></span> <span data-ttu-id="6f036-128">Per testare l'implementazione, aggiungere queste procedure al progetto e chiamare la procedura `testImplements`.</span><span class="sxs-lookup"><span data-stu-id="6f036-128">To test the implementation, add these procedures to your project and call the `testImplements` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="6f036-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f036-129">See also</span></span>

- [<span data-ttu-id="6f036-130">Implements</span><span class="sxs-lookup"><span data-stu-id="6f036-130">Implements</span></span>](../../../visual-basic/language-reference/statements/implements-clause.md)
- [<span data-ttu-id="6f036-131">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="6f036-131">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="6f036-132">Interfacce</span><span class="sxs-lookup"><span data-stu-id="6f036-132">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
