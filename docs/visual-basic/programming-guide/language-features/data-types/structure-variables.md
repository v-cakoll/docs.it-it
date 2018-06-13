---
title: Variabili di struttura (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 0dad7bdcac5428753e252f3b26ca0a127c293a7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648499"
---
# <a name="structure-variables-visual-basic"></a><span data-ttu-id="379ec-102">Variabili di struttura (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="379ec-102">Structure Variables (Visual Basic)</span></span>
<span data-ttu-id="379ec-103">Dopo aver creato una struttura, è possibile dichiarare le variabili a livello di routine sia a livello di modulo come quel tipo.</span><span class="sxs-lookup"><span data-stu-id="379ec-103">Once you have created a structure, you can declare procedure-level and module-level variables as that type.</span></span> <span data-ttu-id="379ec-104">Ad esempio, è possibile creare una struttura che registra le informazioni su un computer.</span><span class="sxs-lookup"><span data-stu-id="379ec-104">For example, you can create a structure that records information about a computer system.</span></span> <span data-ttu-id="379ec-105">Nell'esempio che segue viene illustrato quanto descritto.</span><span class="sxs-lookup"><span data-stu-id="379ec-105">The following example demonstrates this.</span></span>  
  
```  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public purchaseDate As Date  
End Structure  
```  
  
 <span data-ttu-id="379ec-106">È ora possibile dichiarare variabili di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="379ec-106">You can now declare variables of that type.</span></span> <span data-ttu-id="379ec-107">Questa condizione è illustrata la dichiarazione seguente.</span><span class="sxs-lookup"><span data-stu-id="379ec-107">The following declaration illustrates this.</span></span>  
  
```  
Dim mySystem, yourSystem As systemInfo  
```  
  
> [!NOTE]
>  <span data-ttu-id="379ec-108">In classi e moduli, le strutture dichiarate utilizzando il [Dim (istruzione)](../../../../visual-basic/language-reference/statements/dim-statement.md) predefinito l'accesso pubblico.</span><span class="sxs-lookup"><span data-stu-id="379ec-108">In classes and modules, structures declared using the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) default to public access.</span></span> <span data-ttu-id="379ec-109">Se si intende una struttura per essere private, assicurarsi che dichiara la classe utilizzando il [privata](../../../../visual-basic/language-reference/modifiers/private.md) (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="379ec-109">If you intend a structure to be private, make sure you declare it using the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword.</span></span>  
  
## <a name="access-to-structure-values"></a><span data-ttu-id="379ec-110">Accesso ai valori di struttura</span><span class="sxs-lookup"><span data-stu-id="379ec-110">Access to Structure Values</span></span>  
 <span data-ttu-id="379ec-111">Per assegnare e recuperare i valori dagli elementi di una variabile di struttura, utilizzare la stessa sintassi utilizzata per impostare e ottenere le proprietà su un oggetto.</span><span class="sxs-lookup"><span data-stu-id="379ec-111">To assign and retrieve values from the elements of a structure variable, you use the same syntax as you use to set and get properties on an object.</span></span> <span data-ttu-id="379ec-112">Inserire l'operatore di accesso ai membri (`.`) tra il nome di variabile di struttura e il nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="379ec-112">You place the member access operator (`.`) between the structure variable name and the element name.</span></span> <span data-ttu-id="379ec-113">Nell'esempio seguente accede agli elementi delle variabili dichiarate in precedenza come tipo `systemInfo`.</span><span class="sxs-lookup"><span data-stu-id="379ec-113">The following example accesses elements of the variables previously declared as type `systemInfo`.</span></span>  
  
```  
mySystem.cPU = "486"  
Dim tooOld As Boolean  
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True  
```  
  
## <a name="assigning-structure-variables"></a><span data-ttu-id="379ec-114">L'assegnazione delle variabili di struttura</span><span class="sxs-lookup"><span data-stu-id="379ec-114">Assigning Structure Variables</span></span>  
 <span data-ttu-id="379ec-115">È inoltre possibile assegnare una variabile a un'altra se sono entrambi dello stesso tipo di struttura.</span><span class="sxs-lookup"><span data-stu-id="379ec-115">You can also assign one variable to another if both are of the same structure type.</span></span> <span data-ttu-id="379ec-116">Verranno copiati tutti gli elementi di una struttura per gli elementi corrispondenti in altra.</span><span class="sxs-lookup"><span data-stu-id="379ec-116">This copies all the elements of one structure to the corresponding elements in the other.</span></span> <span data-ttu-id="379ec-117">Questa condizione è illustrata la dichiarazione seguente.</span><span class="sxs-lookup"><span data-stu-id="379ec-117">The following declaration illustrates this.</span></span>  
  
```  
yourSystem = mySystem  
```  
  
 <span data-ttu-id="379ec-118">Se un elemento di struttura è un tipo riferimento, ad esempio un `String`, `Object`, o matrice, puntatore ai dati viene copiato.</span><span class="sxs-lookup"><span data-stu-id="379ec-118">If a structure element is a reference type, such as a `String`, `Object`, or array, the pointer to the data is copied.</span></span> <span data-ttu-id="379ec-119">Nell'esempio precedente, se `systemInfo` fosse stata inclusa una variabile oggetto, quindi l'esempio precedente avrebbe consentito la copia del puntatore da `mySystem` a `yourSystem`, e una modifica ai dati dell'oggetto tramite una struttura sarebbe attivo quando vi si accede con la struttura.</span><span class="sxs-lookup"><span data-stu-id="379ec-119">In the previous example, if `systemInfo` had included an object variable, then the preceding example would have copied the pointer from `mySystem` to `yourSystem`, and a change to the object's data through one structure would be in effect when accessed through the other structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="379ec-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="379ec-120">See Also</span></span>  
 [<span data-ttu-id="379ec-121">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="379ec-121">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="379ec-122">Tipi di dati elementari</span><span class="sxs-lookup"><span data-stu-id="379ec-122">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="379ec-123">Tipi di dati compositi</span><span class="sxs-lookup"><span data-stu-id="379ec-123">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [<span data-ttu-id="379ec-124">Tipi valore e tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="379ec-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="379ec-125">Strutture</span><span class="sxs-lookup"><span data-stu-id="379ec-125">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="379ec-126">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="379ec-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="379ec-127">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="379ec-127">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="379ec-128">Strutture e altri elementi di programmazione</span><span class="sxs-lookup"><span data-stu-id="379ec-128">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 [<span data-ttu-id="379ec-129">Strutture e classi</span><span class="sxs-lookup"><span data-stu-id="379ec-129">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [<span data-ttu-id="379ec-130">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="379ec-130">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
