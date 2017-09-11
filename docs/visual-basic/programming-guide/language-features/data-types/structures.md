---
title: Strutture (Visual Basic) | Documenti di Microsoft
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
helpviewer_keywords:
- structures
- user-defined data types, structures
- user-defined types, about user-defined types
- data types [Visual Basic], user-defined
- user-defined data types, about user-defined data types
- types [Visual Basic], user-defined
ms.assetid: 55e86462-5e99-4d33-8018-6d097ca491b2
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d1ba8671af9ff6d50499149fce6d55b3db78ffe0
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="structures-visual-basic"></a><span data-ttu-id="55074-102">Strutture (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55074-102">Structures (Visual Basic)</span></span>
<span data-ttu-id="55074-103">Oggetto *struttura* rappresenta una generalizzazione del tipo definito dall'utente (UDT) supportato dalle versioni precedenti di [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="55074-103">A *structure* is a generalization of the user-defined type (UDT) supported by previous versions of [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="55074-104">Oltre ai campi, le strutture possono esporre proprietà, metodi ed eventi.</span><span class="sxs-lookup"><span data-stu-id="55074-104">In addition to fields, structures can expose properties, methods, and events.</span></span> <span data-ttu-id="55074-105">Una struttura può implementare una o più interfacce ed è possibile dichiarare i livelli di accesso singolo per ogni campo.</span><span class="sxs-lookup"><span data-stu-id="55074-105">A structure can implement one or more interfaces, and you can declare individual access levels for each field.</span></span>  
  
 <span data-ttu-id="55074-106">È possibile combinare gli elementi di dati di tipi diversi per creare una struttura.</span><span class="sxs-lookup"><span data-stu-id="55074-106">You can combine data items of different types to create a structure.</span></span> <span data-ttu-id="55074-107">Una struttura associa uno o più *elementi* tra loro e con la stessa struttura.</span><span class="sxs-lookup"><span data-stu-id="55074-107">A structure associates one or more *elements* with each other and with the structure itself.</span></span> <span data-ttu-id="55074-108">Quando si dichiara una struttura, questo diventa un *tipo di dati composito*, ed è possibile dichiarare le variabili di tale tipo.</span><span class="sxs-lookup"><span data-stu-id="55074-108">When you declare a structure, it becomes a *composite data type*, and you can declare variables of that type.</span></span>  
  
 <span data-ttu-id="55074-109">Strutture sono utili quando si desidera che una singola variabile per contenere più elementi correlati di informazioni.</span><span class="sxs-lookup"><span data-stu-id="55074-109">Structures are useful when you want a single variable to hold several related pieces of information.</span></span> <span data-ttu-id="55074-110">Potrebbe ad esempio, si desidera mantenere nome, numero di telefono e stipendio del dipendente.</span><span class="sxs-lookup"><span data-stu-id="55074-110">For example, you might want to keep an employee's name, telephone extension, and salary together.</span></span> <span data-ttu-id="55074-111">È possibile utilizzare più variabili per queste informazioni oppure è possibile definire una struttura e utilizzarlo per una variabile di singolo dipendente.</span><span class="sxs-lookup"><span data-stu-id="55074-111">You could use several variables for this information, or you could define a structure and use it for a single employee variable.</span></span> <span data-ttu-id="55074-112">Il vantaggio della struttura diventa evidente quando si dispone di più dipendenti e pertanto molte istanze della variabile.</span><span class="sxs-lookup"><span data-stu-id="55074-112">The advantage of the structure becomes apparent when you have many employees and therefore many instances of the variable.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="55074-113">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="55074-113">In This Section</span></span>  
 [<span data-ttu-id="55074-114">Procedura: Dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="55074-114">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 <span data-ttu-id="55074-115">Viene illustrato come dichiarare una struttura e i relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="55074-115">Shows how to declare a structure and its elements.</span></span>  
  
 [<span data-ttu-id="55074-116">Variabili di struttura</span><span class="sxs-lookup"><span data-stu-id="55074-116">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)  
 <span data-ttu-id="55074-117">Viene illustrata l'assegnazione di una struttura a una variabile e accesso ai relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="55074-117">Covers assigning a structure to a variable and accessing its elements.</span></span>  
  
 [<span data-ttu-id="55074-118">Strutture e altri elementi di programmazione</span><span class="sxs-lookup"><span data-stu-id="55074-118">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 <span data-ttu-id="55074-119">Riepiloga l'interagiscono di strutture con matrici, oggetti, procedure e tra loro.</span><span class="sxs-lookup"><span data-stu-id="55074-119">Summarizes how structures interact with arrays, objects, procedures, and each other.</span></span>  
  
 [<span data-ttu-id="55074-120">Strutture e classi</span><span class="sxs-lookup"><span data-stu-id="55074-120">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 <span data-ttu-id="55074-121">Vengono descritte le analogie e differenze tra strutture e classi.</span><span class="sxs-lookup"><span data-stu-id="55074-121">Describes the similarities and differences between structures and classes.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="55074-122">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="55074-122">Related Sections</span></span>  
 [<span data-ttu-id="55074-123">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="55074-123">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="55074-124">Introduce il [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] tipi di dati e viene descritto come utilizzarle.</span><span class="sxs-lookup"><span data-stu-id="55074-124">Introduces the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="55074-125">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="55074-125">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 <span data-ttu-id="55074-126">Vengono elencati i tipi di dati di base forniti da [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="55074-126">Lists the elementary data types supplied by [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>
