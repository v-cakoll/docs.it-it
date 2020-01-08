---
title: Come usare le proprietà indicizzate nella programmazione dell'interoperabilità COM- C# Guida alla programmazione
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
ms.openlocfilehash: aa4dc6da520fc58a99a9691aa39e412468aa02b5
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635314"
---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a><span data-ttu-id="2df56-102">Come utilizzare le proprietà indicizzate nella programmazione dell'interoperabilità COM (C# guida per programmatori)</span><span class="sxs-lookup"><span data-stu-id="2df56-102">How to use indexed properties in COM interop programming (C# Programming Guide)</span></span>
<span data-ttu-id="2df56-103">Le *proprietà indicizzate* migliorano l'uso delle proprietà COM dotate di parametri nella programmazione C#.</span><span class="sxs-lookup"><span data-stu-id="2df56-103">*Indexed properties* improve the way in which COM properties that have parameters are consumed in C# programming.</span></span> <span data-ttu-id="2df56-104">Tali proprietà operano congiuntamente ad altre funzionalità di Visual C#, ad esempio gli [argomenti denominati e facoltativi](../classes-and-structs/named-and-optional-arguments.md), un nuovo tipo ([dynamic](../../language-reference/builtin-types/reference-types.md)) e le [informazioni sul tipo incorporate](../../../standard/assembly/embed-types-visual-studio.md), per migliorare la programmazione di Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="2df56-104">Indexed properties work together with other features in Visual C#, such as [named and optional arguments](../classes-and-structs/named-and-optional-arguments.md), a new type ([dynamic](../../language-reference/builtin-types/reference-types.md)), and [embedded type information](../../../standard/assembly/embed-types-visual-studio.md), to enhance Microsoft Office programming.</span></span>  
  
 <span data-ttu-id="2df56-105">Nelle versioni precedenti di C# i metodi sono accessibili come proprietà solo se il metodo `get` non dispone di parametri e il metodo `set` ha un unico parametro valore.</span><span class="sxs-lookup"><span data-stu-id="2df56-105">In earlier versions of C#, methods are accessible as properties only if the `get` method has no parameters and the `set` method has one and only one value parameter.</span></span> <span data-ttu-id="2df56-106">Non tutte le proprietà COM soddisfano tuttavia tali restrizioni.</span><span class="sxs-lookup"><span data-stu-id="2df56-106">However, not all COM properties meet those restrictions.</span></span> <span data-ttu-id="2df56-107">Ad esempio, la proprietà <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> di Excel possiede una funzione di accesso `get` che richiede un parametro per il nome dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="2df56-107">For example, the Excel <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> property has a `get` accessor that requires a parameter for the name of the range.</span></span> <span data-ttu-id="2df56-108">In passato, poiché non era possibile accedere direttamente alla proprietà `Range`, era necessario usare il metodo`get_Range`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="2df56-108">In the past, because you could not access the `Range` property directly, you had to use the `get_Range` method instead, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#1)]  
  
 <span data-ttu-id="2df56-109">Le proprietà indicizzate consentono invece di scrivere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2df56-109">Indexed properties enable you to write the following instead:</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#2)]  
  
> [!NOTE]
> <span data-ttu-id="2df56-110">Nell'esempio precedente viene usata anche la funzionalità degli [argomenti facoltativi](../classes-and-structs/named-and-optional-arguments.md), che consente di omettere `Type.Missing`.</span><span class="sxs-lookup"><span data-stu-id="2df56-110">The previous example also uses the [optional arguments](../classes-and-structs/named-and-optional-arguments.md) feature, which enables you to omit `Type.Missing`.</span></span>  
  
 <span data-ttu-id="2df56-111">Analogamente, per impostare il valore della proprietà `Value` di un oggetto <xref:Microsoft.Office.Interop.Excel.Range> in C# 3.0 e versioni precedenti, sono necessari due argomenti.</span><span class="sxs-lookup"><span data-stu-id="2df56-111">Similarly to set the value of the `Value` property of a <xref:Microsoft.Office.Interop.Excel.Range> object in C# 3.0 and earlier, two arguments are required.</span></span> <span data-ttu-id="2df56-112">Uno specifica un argomento per un parametro facoltativo che specifica il tipo del valore dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="2df56-112">One supplies an argument for an optional parameter that specifies the type of the range value.</span></span> <span data-ttu-id="2df56-113">L'altro indica il valore per la proprietà `Value`.</span><span class="sxs-lookup"><span data-stu-id="2df56-113">The other supplies the value for the `Value` property.</span></span> <span data-ttu-id="2df56-114">Queste tecniche vengono illustrate negli esempi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="2df56-114">The following examples illustrate these techniques.</span></span> <span data-ttu-id="2df56-115">Entrambe impostano il valore della cella A1 su `Name`.</span><span class="sxs-lookup"><span data-stu-id="2df56-115">Both set the value of the A1 cell to `Name`.</span></span>
  
 [!code-csharp[csProgGuideIndexedProperties#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#3)]  
  
 <span data-ttu-id="2df56-116">Le proprietà indicizzate consentono invece di scrivere il codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="2df56-116">Indexed properties enable you to write the following code instead.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#4)]  
  
 <span data-ttu-id="2df56-117">Non è possibile creare proprietà indicizzate personalizzate.</span><span class="sxs-lookup"><span data-stu-id="2df56-117">You cannot create indexed properties of your own.</span></span> <span data-ttu-id="2df56-118">La funzionalità supporta solo l'utilizzo di proprietà indicizzate esistenti.</span><span class="sxs-lookup"><span data-stu-id="2df56-118">The feature only supports consumption of existing indexed properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2df56-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="2df56-119">Example</span></span>  
 <span data-ttu-id="2df56-120">L'esempio seguente illustra un esempio completo.</span><span class="sxs-lookup"><span data-stu-id="2df56-120">The following code shows a complete example.</span></span> <span data-ttu-id="2df56-121">Per altre informazioni su come configurare un progetto che accede all'API di Office, vedere [come accedere agli oggetti di interoperabilità di Office C# usando le funzionalità di](./how-to-access-office-onterop-objects.md).</span><span class="sxs-lookup"><span data-stu-id="2df56-121">For more information about how to set up a project that accesses the Office API, see [How to access Office interop objects by using C# features](./how-to-access-office-onterop-objects.md).</span></span>
  
 [!code-csharp[csProgGuideIndexedProperties#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguideindexedproperties/cs/program.cs#5)]  
  
## <a name="see-also"></a><span data-ttu-id="2df56-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2df56-122">See also</span></span>

- [<span data-ttu-id="2df56-123">Argomenti denominati e facoltativi</span><span class="sxs-lookup"><span data-stu-id="2df56-123">Named and Optional Arguments</span></span>](../classes-and-structs/named-and-optional-arguments.md)
- [<span data-ttu-id="2df56-124">dynamic</span><span class="sxs-lookup"><span data-stu-id="2df56-124">dynamic</span></span>](../../language-reference/builtin-types/reference-types.md)
- [<span data-ttu-id="2df56-125">Uso del tipo dinamico</span><span class="sxs-lookup"><span data-stu-id="2df56-125">Using Type dynamic</span></span>](../types/using-type-dynamic.md)
- [<span data-ttu-id="2df56-126">Come usare gli argomenti denominati e facoltativi nella programmazione di Office</span><span class="sxs-lookup"><span data-stu-id="2df56-126">How to use named and optional arguments in Office programming</span></span>](../classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)
- [<span data-ttu-id="2df56-127">Come accedere agli oggetti di interoperabilità C# di Office usando le funzionalità</span><span class="sxs-lookup"><span data-stu-id="2df56-127">How to access Office interop objects by using C# features</span></span>](./how-to-access-office-onterop-objects.md)
- [<span data-ttu-id="2df56-128">Procedura dettagliata: Programmazione di Office</span><span class="sxs-lookup"><span data-stu-id="2df56-128">Walkthrough: Office Programming</span></span>](./walkthrough-office-programming.md)
