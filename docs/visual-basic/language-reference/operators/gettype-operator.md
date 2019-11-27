---
title: GetType Operator
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 4e59bcfaa24c9545ed75c6b5c1d29cad398ac2de
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349556"
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="13335-102">Operatore GetType (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="13335-102">GetType Operator (Visual Basic)</span></span>
<span data-ttu-id="13335-103">Restituisce un oggetto <xref:System.Type> per il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="13335-103">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="13335-104">L'oggetto <xref:System.Type> fornisce informazioni sul tipo, ad esempio proprietà, metodi ed eventi.</span><span class="sxs-lookup"><span data-stu-id="13335-104">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13335-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="13335-105">Syntax</span></span>  
  
```vb  
GetType(typename)  
```  
  
## <a name="parameters"></a><span data-ttu-id="13335-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="13335-106">Parameters</span></span>  
  
|<span data-ttu-id="13335-107">Parametro</span><span class="sxs-lookup"><span data-stu-id="13335-107">Parameter</span></span>|<span data-ttu-id="13335-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="13335-108">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="13335-109">Nome del tipo per il quale si desiderano le informazioni.</span><span class="sxs-lookup"><span data-stu-id="13335-109">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13335-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="13335-110">Remarks</span></span>  
 <span data-ttu-id="13335-111">L'operatore `GetType` restituisce l'oggetto <xref:System.Type> per la `typename`specificata.</span><span class="sxs-lookup"><span data-stu-id="13335-111">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="13335-112">È possibile passare il nome di qualsiasi tipo definito in `typename`.</span><span class="sxs-lookup"><span data-stu-id="13335-112">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="13335-113">Il comportamento predefinito include quanto segue:</span><span class="sxs-lookup"><span data-stu-id="13335-113">This includes the following:</span></span>  
  
- <span data-ttu-id="13335-114">Qualsiasi tipo di dati Visual Basic, ad esempio `Boolean` o `Date`.</span><span class="sxs-lookup"><span data-stu-id="13335-114">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
- <span data-ttu-id="13335-115">Qualsiasi .NET Framework classe, struttura, modulo o interfaccia, ad esempio <xref:System.ArgumentException?displayProperty=nameWithType> o <xref:System.Double?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="13335-115">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="13335-116">Qualsiasi classe, struttura, modulo o interfaccia definita dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="13335-116">Any class, structure, module, or interface defined by your application.</span></span>  
  
- <span data-ttu-id="13335-117">Qualsiasi matrice definita dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="13335-117">Any array defined by your application.</span></span>  
  
- <span data-ttu-id="13335-118">Qualsiasi delegato definito dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="13335-118">Any delegate defined by your application.</span></span>  
  
- <span data-ttu-id="13335-119">Qualsiasi enumerazione definita da Visual Basic, .NET Framework o dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="13335-119">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="13335-120">Se si desidera ottenere l'oggetto tipo di una variabile oggetto, utilizzare il metodo <xref:System.Type.GetType%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="13335-120">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="13335-121">L'operatore `GetType` può essere utile nelle circostanze seguenti:</span><span class="sxs-lookup"><span data-stu-id="13335-121">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
- <span data-ttu-id="13335-122">È necessario accedere ai metadati per un tipo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="13335-122">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="13335-123">L'oggetto <xref:System.Type> fornisce metadati, ad esempio i membri del tipo e le informazioni di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="13335-123">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="13335-124">Questa operazione è necessaria, ad esempio, per riflettere un assembly.</span><span class="sxs-lookup"><span data-stu-id="13335-124">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="13335-125">Per altre informazioni, vedere <xref:System.Reflection?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="13335-125">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="13335-126">Si desidera confrontare due riferimenti a oggetti per verificare se fanno riferimento a istanze dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="13335-126">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="13335-127">In caso affermativo, `GetType` restituisce riferimenti allo stesso oggetto <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="13335-127">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13335-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="13335-128">Example</span></span>  
 <span data-ttu-id="13335-129">Negli esempi seguenti viene illustrato l'operatore `GetType` in uso.</span><span class="sxs-lookup"><span data-stu-id="13335-129">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="13335-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13335-130">See also</span></span>

- [<span data-ttu-id="13335-131">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="13335-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="13335-132">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="13335-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="13335-133">Operatori ed espressioni</span><span class="sxs-lookup"><span data-stu-id="13335-133">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
