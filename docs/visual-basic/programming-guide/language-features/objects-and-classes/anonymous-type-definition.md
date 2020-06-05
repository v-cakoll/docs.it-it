---
title: Definizione di tipo anonimo
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
ms.openlocfilehash: 952eb295cc71eab5d0ad6e18f2b697a9b701b434
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404901"
---
# <a name="anonymous-type-definition-visual-basic"></a><span data-ttu-id="f07ed-102">Definizione di tipo anonimo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f07ed-102">Anonymous Type Definition (Visual Basic)</span></span>

<span data-ttu-id="f07ed-103">In risposta alla dichiarazione di un'istanza di un tipo anonimo, il compilatore crea una nuova definizione di classe che contiene le proprietà specificate per il tipo.</span><span class="sxs-lookup"><span data-stu-id="f07ed-103">In response to the declaration of an instance of an anonymous type, the compiler creates a new class definition that contains the specified properties for the type.</span></span>

## <a name="compiler-generated-code"></a><span data-ttu-id="f07ed-104">Codice generato dal compilatore</span><span class="sxs-lookup"><span data-stu-id="f07ed-104">Compiler-Generated Code</span></span>

<span data-ttu-id="f07ed-105">Per la definizione seguente di `product` , il compilatore crea una nuova definizione di classe che contiene le proprietà `Name` , `Price` e `OnHand` .</span><span class="sxs-lookup"><span data-stu-id="f07ed-105">For the following definition of `product`, the compiler creates a new class definition that contains properties `Name`, `Price`, and `OnHand`.</span></span>

[!code-vb[VbVbalrAnonymousTypes#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#25)]

<span data-ttu-id="f07ed-106">La definizione della classe contiene definizioni di proprietà simili a quelle riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="f07ed-106">The class definition contains property definitions similar to the following.</span></span> <span data-ttu-id="f07ed-107">Si noti che non esiste alcun `Set` metodo per le proprietà chiave.</span><span class="sxs-lookup"><span data-stu-id="f07ed-107">Notice that there is no `Set` method for the key properties.</span></span> <span data-ttu-id="f07ed-108">I valori delle proprietà chiave sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="f07ed-108">The values of key properties are read-only.</span></span>

```vb
Public Class $Anonymous1
    Private _name As String
    Private _price As Double
    Private _onHand As Integer
     Public ReadOnly Property Name() As String
        Get
            Return _name
        End Get
    End Property

    Public ReadOnly Property Price() As Double
        Get
            Return _price
        End Get
    End Property

    Public Property OnHand() As Integer
        Get
            Return _onHand
        End Get
        Set(ByVal Value As Integer)
            _onHand = Value
        End Set
    End Property

End Class
```

<span data-ttu-id="f07ed-109">Inoltre, le definizioni di tipo anonimo contengono un costruttore senza parametri.</span><span class="sxs-lookup"><span data-stu-id="f07ed-109">In addition, anonymous type definitions contain a parameterless constructor.</span></span> <span data-ttu-id="f07ed-110">I costruttori che richiedono parametri non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="f07ed-110">Constructors that require parameters are not permitted.</span></span>

<span data-ttu-id="f07ed-111">Se una dichiarazione di tipo anonimo contiene almeno una proprietà chiave, la definizione del tipo esegue l'override di tre membri ereditati da <xref:System.Object> : <xref:System.Object.Equals%2A> , <xref:System.Object.GetHashCode%2A> e <xref:System.Object.ToString%2A> .</span><span class="sxs-lookup"><span data-stu-id="f07ed-111">If an anonymous type declaration contains at least one key property, the type definition overrides three members inherited from <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="f07ed-112">Se non viene dichiarata alcuna proprietà chiave, <xref:System.Object.ToString%2A> viene eseguito l'override di.</span><span class="sxs-lookup"><span data-stu-id="f07ed-112">If no key properties are declared, only <xref:System.Object.ToString%2A> is overridden.</span></span> <span data-ttu-id="f07ed-113">Le sostituzioni forniscono le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="f07ed-113">The overrides provide the following functionality:</span></span>

- <span data-ttu-id="f07ed-114">`Equals`restituisce `True` se due istanze di tipo anonimo sono la stessa istanza o se soddisfano le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f07ed-114">`Equals` returns `True` if two anonymous type instances are the same instance, or if they meet the following conditions:</span></span>

  - <span data-ttu-id="f07ed-115">Hanno lo stesso numero di proprietà.</span><span class="sxs-lookup"><span data-stu-id="f07ed-115">They have the same number of properties.</span></span>

  - <span data-ttu-id="f07ed-116">Le proprietà vengono dichiarate nello stesso ordine, con gli stessi nomi e gli stessi tipi dedotti.</span><span class="sxs-lookup"><span data-stu-id="f07ed-116">The properties are declared in the same order, with the same names and the same inferred types.</span></span> <span data-ttu-id="f07ed-117">I confronti tra nomi non fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="f07ed-117">Name comparisons are not case-sensitive.</span></span>

  - <span data-ttu-id="f07ed-118">Almeno una delle proprietà è una proprietà chiave e la `Key` parola chiave viene applicata alle stesse proprietà.</span><span class="sxs-lookup"><span data-stu-id="f07ed-118">At least one of the properties is a key property, and the `Key` keyword is applied to the same properties.</span></span>

  - <span data-ttu-id="f07ed-119">Il confronto di ogni coppia corrispondente di proprietà chiave restituisce `True` .</span><span class="sxs-lookup"><span data-stu-id="f07ed-119">Comparison of each corresponding pair of key properties returns `True`.</span></span>

    <span data-ttu-id="f07ed-120">Negli esempi seguenti, ad esempio, `Equals` restituisce `True` solo per `employee01` e `employee08` .</span><span class="sxs-lookup"><span data-stu-id="f07ed-120">For example, in the following examples, `Equals` returns `True` only for `employee01` and `employee08`.</span></span> <span data-ttu-id="f07ed-121">Il commento prima di ogni riga specifica il motivo per cui la nuova istanza non corrisponde `employee01` .</span><span class="sxs-lookup"><span data-stu-id="f07ed-121">The comment before each line specifies the reason why the new instance does not match `employee01`.</span></span>

    [!code-vb[VbVbalrAnonymousTypes#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#24)]

- <span data-ttu-id="f07ed-122">`GetHashcode`fornisce un algoritmo GetHashCode univoco in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="f07ed-122">`GetHashcode` provides an appropriately unique GetHashCode algorithm.</span></span> <span data-ttu-id="f07ed-123">L'algoritmo usa solo le proprietà chiave per calcolare il codice hash.</span><span class="sxs-lookup"><span data-stu-id="f07ed-123">The algorithm uses only the key properties to compute the hash code.</span></span>

- <span data-ttu-id="f07ed-124">`ToString`Restituisce una stringa di valori di proprietà concatenati, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="f07ed-124">`ToString` returns a string of concatenated property values, as shown in the following example.</span></span> <span data-ttu-id="f07ed-125">Sono incluse entrambe le proprietà chiave e non chiave.</span><span class="sxs-lookup"><span data-stu-id="f07ed-125">Both key and non-key properties are included.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#29)]

<span data-ttu-id="f07ed-126">Le proprietà denominate in modo esplicito di un tipo anonimo non possono essere in conflitto con questi metodi generati.</span><span class="sxs-lookup"><span data-stu-id="f07ed-126">Explicitly named properties of an anonymous type cannot conflict with these generated methods.</span></span> <span data-ttu-id="f07ed-127">Ovvero, non è possibile utilizzare `.Equals` , `.GetHashCode` o `.ToString` per assegnare un nome a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="f07ed-127">That is, you cannot use `.Equals`, `.GetHashCode`, or `.ToString` to name a property.</span></span>

<span data-ttu-id="f07ed-128">Anche le definizioni di tipo anonimo che includono almeno una proprietà chiave implementano l' <xref:System.IEquatable%601?displayProperty=nameWithType> interfaccia, dove `T` è il tipo del tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="f07ed-128">Anonymous type definitions that include at least one key property also implement the <xref:System.IEquatable%601?displayProperty=nameWithType> interface, where `T` is the type of the anonymous type.</span></span>

> [!NOTE]
> <span data-ttu-id="f07ed-129">Le dichiarazioni di tipo anonimo creano lo stesso tipo anonimo solo se si trovano nello stesso assembly, le relative proprietà hanno gli stessi nomi e gli stessi tipi inferiti, le proprietà vengono dichiarate nello stesso ordine e le stesse proprietà sono contrassegnate come proprietà chiave.</span><span class="sxs-lookup"><span data-stu-id="f07ed-129">Anonymous type declarations create the same anonymous type only if they occur in the same assembly, their properties have the same names and the same inferred types, the properties are declared in the same order, and the same properties are marked as key properties.</span></span>

## <a name="see-also"></a><span data-ttu-id="f07ed-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f07ed-130">See also</span></span>

- [<span data-ttu-id="f07ed-131">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="f07ed-131">Anonymous Types</span></span>](anonymous-types.md)
- [<span data-ttu-id="f07ed-132">Procedura: dedurre tipi e nomi di proprietà nelle dichiarazioni di tipo anonimo</span><span class="sxs-lookup"><span data-stu-id="f07ed-132">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
