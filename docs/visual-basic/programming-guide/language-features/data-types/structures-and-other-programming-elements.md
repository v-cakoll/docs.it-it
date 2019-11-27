---
title: Strutture e altri elementi di programmazione
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], arrays
- procedures [Visual Basic], structures as arguments to
- objects [Visual Basic], structure elements
- arrays [Visual Basic], structure elements
- nested structures [Visual Basic]
ms.assetid: 0f849313-ccd2-4c9a-acb9-69de6751c088
ms.openlocfilehash: 309d0e5214897675e1758bd98b964392b379ca1b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346112"
---
# <a name="structures-and-other-programming-elements-visual-basic"></a><span data-ttu-id="9608d-102">Strutture e altri elementi di programmazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9608d-102">Structures and Other Programming Elements (Visual Basic)</span></span>
<span data-ttu-id="9608d-103">È possibile utilizzare le strutture insieme a matrici, oggetti e procedure, nonché reciprocamente.</span><span class="sxs-lookup"><span data-stu-id="9608d-103">You can use structures in conjunction with arrays, objects, and procedures, as well as with each other.</span></span> <span data-ttu-id="9608d-104">Le interazioni utilizzano la stessa sintassi di questi elementi.</span><span class="sxs-lookup"><span data-stu-id="9608d-104">The interactions use the same syntax as these elements use individually.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9608d-105">Non è possibile inizializzare alcuno degli elementi della struttura nella dichiarazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="9608d-105">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="9608d-106">È possibile assegnare valori solo agli elementi di una variabile dichiarata come tipo di struttura.</span><span class="sxs-lookup"><span data-stu-id="9608d-106">You can assign values only to elements of a variable that has been declared to be of a structure type.</span></span>  
  
## <a name="structures-and-arrays"></a><span data-ttu-id="9608d-107">Strutture e matrici</span><span class="sxs-lookup"><span data-stu-id="9608d-107">Structures and Arrays</span></span>  
 <span data-ttu-id="9608d-108">Una struttura può contenere una matrice come uno o più dei relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="9608d-108">A structure can contain an array as one or more of its elements.</span></span> <span data-ttu-id="9608d-109">Ciò è illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9608d-109">The following example illustrates this.</span></span>  
  
```vb  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure   
```  
  
 <span data-ttu-id="9608d-110">È possibile accedere ai valori di una matrice all'interno di una struttura nello stesso modo in cui si accede a una proprietà in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="9608d-110">You access the values of an array within a structure the same way you access a property on an object.</span></span> <span data-ttu-id="9608d-111">Ciò è illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9608d-111">The following example illustrates this.</span></span>  
  
```vb  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 <span data-ttu-id="9608d-112">È anche possibile dichiarare una matrice di strutture.</span><span class="sxs-lookup"><span data-stu-id="9608d-112">You can also declare an array of structures.</span></span> <span data-ttu-id="9608d-113">Ciò è illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9608d-113">The following example illustrates this.</span></span>  
  
```vb  
Dim allSystems(100) As systemInfo  
```  
  
 <span data-ttu-id="9608d-114">Si seguono le stesse regole per accedere ai componenti di questa architettura di dati.</span><span class="sxs-lookup"><span data-stu-id="9608d-114">You follow the same rules to access the components of this data architecture.</span></span> <span data-ttu-id="9608d-115">Ciò è illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9608d-115">The following example illustrates this.</span></span>  
  
```vb  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## <a name="structures-and-objects"></a><span data-ttu-id="9608d-116">Strutture e oggetti</span><span class="sxs-lookup"><span data-stu-id="9608d-116">Structures and Objects</span></span>  
 <span data-ttu-id="9608d-117">Una struttura può contenere un oggetto come uno o più elementi.</span><span class="sxs-lookup"><span data-stu-id="9608d-117">A structure can contain an object as one or more of its elements.</span></span> <span data-ttu-id="9608d-118">Ciò è illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9608d-118">The following example illustrates this.</span></span>  
  
```vb  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 <span data-ttu-id="9608d-119">È consigliabile usare una classe di oggetti specifica in una dichiarazione di questo tipo, anziché `Object`.</span><span class="sxs-lookup"><span data-stu-id="9608d-119">You should use a specific object class in such a declaration, rather than `Object`.</span></span>  
  
## <a name="structures-and-procedures"></a><span data-ttu-id="9608d-120">Strutture e procedure</span><span class="sxs-lookup"><span data-stu-id="9608d-120">Structures and Procedures</span></span>  
 <span data-ttu-id="9608d-121">È possibile passare una struttura come argomento di routine.</span><span class="sxs-lookup"><span data-stu-id="9608d-121">You can pass a structure as a procedure argument.</span></span> <span data-ttu-id="9608d-122">Ciò è illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9608d-122">The following example illustrates this.</span></span>  
  
```vb  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 <span data-ttu-id="9608d-123">Nell'esempio precedente la struttura viene passata *per riferimento*, che consente alla procedura di modificarne gli elementi in modo che le modifiche abbiano effetto nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="9608d-123">The preceding example passes the structure *by reference*, which allows the procedure to modify its elements so that the changes take effect in the calling code.</span></span> <span data-ttu-id="9608d-124">Se si desidera proteggere una struttura in base a tale modifica, passarla per valore.</span><span class="sxs-lookup"><span data-stu-id="9608d-124">If you want to protect a structure against such modification, pass it by value.</span></span>  
  
 <span data-ttu-id="9608d-125">È anche possibile restituire una struttura da una routine `Function`.</span><span class="sxs-lookup"><span data-stu-id="9608d-125">You can also return a structure from a `Function` procedure.</span></span> <span data-ttu-id="9608d-126">Ciò è illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9608d-126">The following example illustrates this.</span></span>  
  
```vb  
Dim allSystems(100) As systemInfo  
Function findByDate(ByVal searchDate As Date) As systemInfo  
    Dim i As Integer  
    For i = 1 To 100  
        If allSystems(i).purchaseDate = searchDate Then Return allSystems(i)  
    Next i  
   ' Process error: system with desired purchase date not found.  
End Function  
```  
  
## <a name="structures-within-structures"></a><span data-ttu-id="9608d-127">Strutture all'interno di strutture</span><span class="sxs-lookup"><span data-stu-id="9608d-127">Structures Within Structures</span></span>  
 <span data-ttu-id="9608d-128">Le strutture possono contenere altre strutture.</span><span class="sxs-lookup"><span data-stu-id="9608d-128">Structures can contain other structures.</span></span> <span data-ttu-id="9608d-129">Ciò è illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9608d-129">The following example illustrates this.</span></span>  
  
```vb  
Public Structure driveInfo  
    Public type As String  
    Public size As Long  
End Structure  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As driveInfo  
    Public purchaseDate As Date  
End Structure  
```  
  
```vb  
Dim allSystems(100) As systemInfo  
ReDim allSystems(1).diskDrives(3)  
allSystems(1).diskDrives(0).type = "Floppy"  
```  
  
 <span data-ttu-id="9608d-130">È anche possibile usare questa tecnica per incapsulare una struttura definita in un modulo all'interno di una struttura definita in un modulo diverso.</span><span class="sxs-lookup"><span data-stu-id="9608d-130">You can also use this technique to encapsulate a structure defined in one module within a structure defined in a different module.</span></span>  
  
 <span data-ttu-id="9608d-131">Le strutture possono contenere altre strutture a una profondità arbitraria.</span><span class="sxs-lookup"><span data-stu-id="9608d-131">Structures can contain other structures to an arbitrary depth.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9608d-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9608d-132">See also</span></span>

- [<span data-ttu-id="9608d-133">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="9608d-133">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="9608d-134">Tipi di dati elementari</span><span class="sxs-lookup"><span data-stu-id="9608d-134">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="9608d-135">Tipi di dati compositi</span><span class="sxs-lookup"><span data-stu-id="9608d-135">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="9608d-136">Tipi valore e tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="9608d-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="9608d-137">Strutture</span><span class="sxs-lookup"><span data-stu-id="9608d-137">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="9608d-138">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="9608d-138">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="9608d-139">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="9608d-139">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="9608d-140">Variabili di struttura</span><span class="sxs-lookup"><span data-stu-id="9608d-140">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [<span data-ttu-id="9608d-141">Strutture e classi</span><span class="sxs-lookup"><span data-stu-id="9608d-141">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="9608d-142">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="9608d-142">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
