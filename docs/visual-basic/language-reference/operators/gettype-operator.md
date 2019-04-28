---
title: Operatore GetType (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 34ab192814583db5cdc0d0183c73cc22b8633e9c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663609"
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="e2a52-102">Operatore GetType (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e2a52-102">GetType Operator (Visual Basic)</span></span>
<span data-ttu-id="e2a52-103">Restituisce un <xref:System.Type> oggetto per il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="e2a52-103">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="e2a52-104">Il <xref:System.Type> oggetto fornisce informazioni sul tipo, ad esempio le proprietà, metodi ed eventi.</span><span class="sxs-lookup"><span data-stu-id="e2a52-104">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2a52-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2a52-105">Syntax</span></span>  
  
```  
GetType(typename)  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2a52-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e2a52-106">Parameters</span></span>  
  
|<span data-ttu-id="e2a52-107">Parametro</span><span class="sxs-lookup"><span data-stu-id="e2a52-107">Parameter</span></span>|<span data-ttu-id="e2a52-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2a52-108">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="e2a52-109">Il nome del tipo per cui si desidera ottenere informazioni.</span><span class="sxs-lookup"><span data-stu-id="e2a52-109">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2a52-110">Note</span><span class="sxs-lookup"><span data-stu-id="e2a52-110">Remarks</span></span>  
 <span data-ttu-id="e2a52-111">Il `GetType` operatore restituisce il <xref:System.Type> oggetto per l'oggetto specificato `typename`.</span><span class="sxs-lookup"><span data-stu-id="e2a52-111">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="e2a52-112">È possibile passare il nome di qualsiasi tipo definito in `typename`.</span><span class="sxs-lookup"><span data-stu-id="e2a52-112">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="e2a52-113">Il comportamento predefinito include quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e2a52-113">This includes the following:</span></span>  
  
- <span data-ttu-id="e2a52-114">Tutti i dati di Visual Basic digitare, ad esempio `Boolean` o `Date`.</span><span class="sxs-lookup"><span data-stu-id="e2a52-114">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
- <span data-ttu-id="e2a52-115">Qualsiasi classe .NET Framework, struttura, modulo o interfaccia, ad esempio <xref:System.ArgumentException?displayProperty=nameWithType> o <xref:System.Double?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e2a52-115">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="e2a52-116">Qualsiasi classe, struttura, modulo o interfaccia definita dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e2a52-116">Any class, structure, module, or interface defined by your application.</span></span>  
  
- <span data-ttu-id="e2a52-117">Qualsiasi matrice definita dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e2a52-117">Any array defined by your application.</span></span>  
  
- <span data-ttu-id="e2a52-118">Qualsiasi delegato definito dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e2a52-118">Any delegate defined by your application.</span></span>  
  
- <span data-ttu-id="e2a52-119">Qualsiasi enumerazione definito da Visual Basic, .NET Framework o l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e2a52-119">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="e2a52-120">Se si desidera ottenere l'oggetto di tipo di una variabile oggetto, usare il <xref:System.Type.GetType%2A?displayProperty=nameWithType> (metodo).</span><span class="sxs-lookup"><span data-stu-id="e2a52-120">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="e2a52-121">Il `GetType` operatore può essere utile nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e2a52-121">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
- <span data-ttu-id="e2a52-122">È necessario accedere ai metadati per un tipo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e2a52-122">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="e2a52-123">Il <xref:System.Type> oggetto fornisce metadati quali i membri dei tipi e le informazioni di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e2a52-123">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="e2a52-124">È necessario, ad esempio, in modo da riflettere su un assembly.</span><span class="sxs-lookup"><span data-stu-id="e2a52-124">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="e2a52-125">Per altre informazioni, vedere <xref:System.Reflection?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e2a52-125">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="e2a52-126">Si desidera confrontare due riferimenti a oggetti per verificare se fanno riferimento a istanze dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="e2a52-126">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="e2a52-127">In caso affermativo, `GetType` restituisce i riferimenti allo stesso <xref:System.Type> oggetto.</span><span class="sxs-lookup"><span data-stu-id="e2a52-127">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2a52-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="e2a52-128">Example</span></span>  
 <span data-ttu-id="e2a52-129">Gli esempi seguenti illustrano il `GetType` operatore in uso.</span><span class="sxs-lookup"><span data-stu-id="e2a52-129">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="e2a52-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2a52-130">See also</span></span>

- [<span data-ttu-id="e2a52-131">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e2a52-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="e2a52-132">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="e2a52-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="e2a52-133">Operatori ed espressioni</span><span class="sxs-lookup"><span data-stu-id="e2a52-133">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
