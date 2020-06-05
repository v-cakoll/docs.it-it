---
title: GetType Operator
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 37644a9c37ffde084120c5f1e1ee8c87a04ffc3c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371155"
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="fd900-102">Operatore GetType (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd900-102">GetType Operator (Visual Basic)</span></span>
<span data-ttu-id="fd900-103">Restituisce un <xref:System.Type> oggetto per il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="fd900-103">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="fd900-104">L' <xref:System.Type> oggetto fornisce informazioni sul tipo, ad esempio proprietà, metodi ed eventi.</span><span class="sxs-lookup"><span data-stu-id="fd900-104">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd900-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fd900-105">Syntax</span></span>  
  
```vb  
GetType(typename)  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd900-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="fd900-106">Parameters</span></span>  
  
|<span data-ttu-id="fd900-107">Parametro</span><span class="sxs-lookup"><span data-stu-id="fd900-107">Parameter</span></span>|<span data-ttu-id="fd900-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd900-108">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="fd900-109">Nome del tipo per il quale si desiderano le informazioni.</span><span class="sxs-lookup"><span data-stu-id="fd900-109">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd900-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="fd900-110">Remarks</span></span>  
 <span data-ttu-id="fd900-111">L' `GetType` operatore restituisce l' <xref:System.Type> oggetto per l'oggetto specificato `typename` .</span><span class="sxs-lookup"><span data-stu-id="fd900-111">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="fd900-112">È possibile passare il nome di qualsiasi tipo definito in `typename` .</span><span class="sxs-lookup"><span data-stu-id="fd900-112">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="fd900-113">Sono inclusi gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd900-113">This includes the following:</span></span>  
  
- <span data-ttu-id="fd900-114">Qualsiasi tipo di dati Visual Basic, ad esempio `Boolean` o `Date` .</span><span class="sxs-lookup"><span data-stu-id="fd900-114">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
- <span data-ttu-id="fd900-115">Qualsiasi .NET Framework classe, struttura, modulo o interfaccia, ad esempio <xref:System.ArgumentException?displayProperty=nameWithType> o <xref:System.Double?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="fd900-115">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="fd900-116">Qualsiasi classe, struttura, modulo o interfaccia definita dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fd900-116">Any class, structure, module, or interface defined by your application.</span></span>  
  
- <span data-ttu-id="fd900-117">Qualsiasi matrice definita dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fd900-117">Any array defined by your application.</span></span>  
  
- <span data-ttu-id="fd900-118">Qualsiasi delegato definito dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fd900-118">Any delegate defined by your application.</span></span>  
  
- <span data-ttu-id="fd900-119">Qualsiasi enumerazione definita da Visual Basic, .NET Framework o dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fd900-119">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="fd900-120">Se si desidera ottenere l'oggetto tipo di una variabile oggetto, utilizzare il <xref:System.Type.GetType%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="fd900-120">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="fd900-121">L' `GetType` operatore può essere utile nelle circostanze seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd900-121">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
- <span data-ttu-id="fd900-122">È necessario accedere ai metadati per un tipo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fd900-122">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="fd900-123">L' <xref:System.Type> oggetto fornisce metadati quali i membri del tipo e le informazioni sulla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fd900-123">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="fd900-124">Questa operazione è necessaria, ad esempio, per riflettere un assembly.</span><span class="sxs-lookup"><span data-stu-id="fd900-124">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="fd900-125">Per altre informazioni, vedere <xref:System.Reflection?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fd900-125">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="fd900-126">Si desidera confrontare due riferimenti a oggetti per verificare se fanno riferimento a istanze dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="fd900-126">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="fd900-127">In caso affermativo, `GetType` restituisce riferimenti allo stesso <xref:System.Type> oggetto.</span><span class="sxs-lookup"><span data-stu-id="fd900-127">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd900-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="fd900-128">Example</span></span>  
 <span data-ttu-id="fd900-129">Negli esempi seguenti viene illustrato l' `GetType` operatore in uso.</span><span class="sxs-lookup"><span data-stu-id="fd900-129">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="fd900-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd900-130">See also</span></span>

- [<span data-ttu-id="fd900-131">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fd900-131">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="fd900-132">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="fd900-132">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="fd900-133">Operatori ed espressioni</span><span class="sxs-lookup"><span data-stu-id="fd900-133">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
