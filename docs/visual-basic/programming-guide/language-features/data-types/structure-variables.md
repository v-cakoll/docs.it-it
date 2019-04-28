---
title: Variabili di struttura (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 9a6e542e297a17f44d929235530ae6058cf13a36
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663388"
---
# <a name="structure-variables-visual-basic"></a><span data-ttu-id="203dc-102">Variabili di struttura (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="203dc-102">Structure Variables (Visual Basic)</span></span>
<span data-ttu-id="203dc-103">Dopo aver creato una struttura, è possibile dichiarare le variabili a livello di routine e a livello di modulo di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="203dc-103">Once you have created a structure, you can declare procedure-level and module-level variables as that type.</span></span> <span data-ttu-id="203dc-104">Ad esempio, è possibile creare una struttura di registrare le informazioni sul sistema.</span><span class="sxs-lookup"><span data-stu-id="203dc-104">For example, you can create a structure that records information about a computer system.</span></span> <span data-ttu-id="203dc-105">Nell'esempio che segue viene illustrato quanto descritto.</span><span class="sxs-lookup"><span data-stu-id="203dc-105">The following example demonstrates this.</span></span>  
  
```  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public purchaseDate As Date  
End Structure  
```  
  
 <span data-ttu-id="203dc-106">È ora possibile dichiarare variabili di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="203dc-106">You can now declare variables of that type.</span></span> <span data-ttu-id="203dc-107">Questa condizione è illustrata la dichiarazione seguente.</span><span class="sxs-lookup"><span data-stu-id="203dc-107">The following declaration illustrates this.</span></span>  
  
```  
Dim mySystem, yourSystem As systemInfo  
```  
  
> [!NOTE]
>  <span data-ttu-id="203dc-108">Nelle classi e moduli, strutture dichiarate utilizzando il [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) predefinito per l'accesso pubblico.</span><span class="sxs-lookup"><span data-stu-id="203dc-108">In classes and modules, structures declared using the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) default to public access.</span></span> <span data-ttu-id="203dc-109">Se si intende una struttura a essere private, assicurarsi di dichiarare usando il [privato](../../../../visual-basic/language-reference/modifiers/private.md) (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="203dc-109">If you intend a structure to be private, make sure you declare it using the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword.</span></span>  
  
## <a name="access-to-structure-values"></a><span data-ttu-id="203dc-110">Accesso ai valori di struttura</span><span class="sxs-lookup"><span data-stu-id="203dc-110">Access to Structure Values</span></span>  
 <span data-ttu-id="203dc-111">Per assegnare e recuperare i valori dagli elementi di una variabile di struttura, utilizzare la stessa sintassi utilizzata per impostare e ottenere le proprietà su un oggetto.</span><span class="sxs-lookup"><span data-stu-id="203dc-111">To assign and retrieve values from the elements of a structure variable, you use the same syntax as you use to set and get properties on an object.</span></span> <span data-ttu-id="203dc-112">Si inserisce l'operatore di accesso ai membri (`.`) tra il nome di variabile di struttura e il nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="203dc-112">You place the member access operator (`.`) between the structure variable name and the element name.</span></span> <span data-ttu-id="203dc-113">Nell'esempio seguente accede agli elementi delle variabili dichiarate in precedenza come tipo `systemInfo`.</span><span class="sxs-lookup"><span data-stu-id="203dc-113">The following example accesses elements of the variables previously declared as type `systemInfo`.</span></span>  
  
```  
mySystem.cPU = "486"  
Dim tooOld As Boolean  
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True  
```  
  
## <a name="assigning-structure-variables"></a><span data-ttu-id="203dc-114">Assegnazione di variabili di struttura</span><span class="sxs-lookup"><span data-stu-id="203dc-114">Assigning Structure Variables</span></span>  
 <span data-ttu-id="203dc-115">È anche possibile assegnare una variabile a un altro se entrambi sono dello stesso tipo struttura.</span><span class="sxs-lookup"><span data-stu-id="203dc-115">You can also assign one variable to another if both are of the same structure type.</span></span> <span data-ttu-id="203dc-116">Questa copia tutti gli elementi di una struttura per gli elementi corrispondenti in altra.</span><span class="sxs-lookup"><span data-stu-id="203dc-116">This copies all the elements of one structure to the corresponding elements in the other.</span></span> <span data-ttu-id="203dc-117">Questa condizione è illustrata la dichiarazione seguente.</span><span class="sxs-lookup"><span data-stu-id="203dc-117">The following declaration illustrates this.</span></span>  
  
```  
yourSystem = mySystem  
```  
  
 <span data-ttu-id="203dc-118">Se un elemento di struttura è un tipo riferimento, ad esempio un `String`, `Object`, o matrice, il puntatore ai dati viene copiato.</span><span class="sxs-lookup"><span data-stu-id="203dc-118">If a structure element is a reference type, such as a `String`, `Object`, or array, the pointer to the data is copied.</span></span> <span data-ttu-id="203dc-119">Nell'esempio precedente, se `systemInfo` fosse stata inclusa una variabile oggetto, quindi l'esempio precedente sarebbe stato copiato il puntatore dal `mySystem` a `yourSystem`, e una modifica ai dati dell'oggetto tramite una sola struttura sarebbe attivo quando si accede tramite la struttura.</span><span class="sxs-lookup"><span data-stu-id="203dc-119">In the previous example, if `systemInfo` had included an object variable, then the preceding example would have copied the pointer from `mySystem` to `yourSystem`, and a change to the object's data through one structure would be in effect when accessed through the other structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="203dc-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="203dc-120">See also</span></span>

- [<span data-ttu-id="203dc-121">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="203dc-121">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="203dc-122">Tipi di dati elementari</span><span class="sxs-lookup"><span data-stu-id="203dc-122">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="203dc-123">Tipi di dati compositi</span><span class="sxs-lookup"><span data-stu-id="203dc-123">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="203dc-124">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="203dc-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="203dc-125">Strutture</span><span class="sxs-lookup"><span data-stu-id="203dc-125">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="203dc-126">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="203dc-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="203dc-127">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="203dc-127">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="203dc-128">Strutture e altri elementi di programmazione</span><span class="sxs-lookup"><span data-stu-id="203dc-128">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [<span data-ttu-id="203dc-129">Strutture e classi</span><span class="sxs-lookup"><span data-stu-id="203dc-129">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="203dc-130">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="203dc-130">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
