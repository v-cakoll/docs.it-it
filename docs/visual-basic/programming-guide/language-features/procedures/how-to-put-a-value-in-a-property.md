---
title: 'Procedura: inserire un valore in una proprietà (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
ms.openlocfilehash: 29e68ca2b9436921c81346eb1def2417157aae9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650371"
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a><span data-ttu-id="62416-102">Procedura: inserire un valore in una proprietà (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62416-102">How to: Put a Value in a Property (Visual Basic)</span></span>
<span data-ttu-id="62416-103">Archiviare un valore in una proprietà inserendo il nome della proprietà sul lato sinistro di un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="62416-103">You store a value in a property by putting the property name on the left side of an assignment statement.</span></span>  
  
 <span data-ttu-id="62416-104">La proprietà `Set` procedure archivia un valore, ma non chiamare in modo esplicito, in base al nome.</span><span class="sxs-lookup"><span data-stu-id="62416-104">The property's `Set` procedure stores a value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="62416-105">Utilizzare la proprietà, esattamente come si utilizzerebbe una variabile.</span><span class="sxs-lookup"><span data-stu-id="62416-105">You use the property just as you would use a variable.</span></span> <span data-ttu-id="62416-106">Visual Basic effettua le chiamate alle routine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="62416-106">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-store-a-value-in-a-property"></a><span data-ttu-id="62416-107">Per archiviare un valore in una proprietà</span><span class="sxs-lookup"><span data-stu-id="62416-107">To store a value in a property</span></span>  
  
1.  <span data-ttu-id="62416-108">Utilizzare il nome della proprietà sul lato sinistro di un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="62416-108">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="62416-109">Nell'esempio seguente imposta il valore di Visual Basic `TimeOfDay` proprietà a mezzogiorno, chiamata di implicitamente relativo `Set` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="62416-109">The following example sets the value of the Visual Basic `TimeOfDay` property to noon, implicitly calling its `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-put-a-value-in-a-property_1.vb)]  
  
2.  <span data-ttu-id="62416-110">Se la proprietà accetta argomenti, dopo il nome della proprietà con le parentesi per racchiudere l'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="62416-110">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="62416-111">Se non sono presenti argomenti, è possibile omettere le parentesi.</span><span class="sxs-lookup"><span data-stu-id="62416-111">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="62416-112">Posizionare gli argomenti nell'elenco di argomenti all'interno delle parentesi, separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="62416-112">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="62416-113">Assicurarsi che fornire gli argomenti nello stesso ordine in cui la proprietà definisce i parametri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="62416-113">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
4.  <span data-ttu-id="62416-114">Il valore generato sul lato destro dell'istruzione di assegnazione è archiviato nella proprietà.</span><span class="sxs-lookup"><span data-stu-id="62416-114">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62416-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62416-115">See Also</span></span>  
 <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>  
 [<span data-ttu-id="62416-116">Routine Property</span><span class="sxs-lookup"><span data-stu-id="62416-116">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="62416-117">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="62416-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="62416-118">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="62416-118">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="62416-119">Differenze tra proprietà e variabili in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="62416-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="62416-120">Procedura: Creare una proprietà</span><span class="sxs-lookup"><span data-stu-id="62416-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="62416-121">Procedura: Dichiarare una proprietà con livelli di accesso misti</span><span class="sxs-lookup"><span data-stu-id="62416-121">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [<span data-ttu-id="62416-122">Procedura: Chiamare una routine di proprietà</span><span class="sxs-lookup"><span data-stu-id="62416-122">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="62416-123">Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="62416-123">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="62416-124">Procedura: Ottenere un valore da una proprietà</span><span class="sxs-lookup"><span data-stu-id="62416-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
