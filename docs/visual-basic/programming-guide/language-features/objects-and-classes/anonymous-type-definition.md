---
title: Definizione di tipo anonimo (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
ms.openlocfilehash: 832d56f5c51aea87185f36ec306c3fec036a40e0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61780848"
---
# <a name="anonymous-type-definition-visual-basic"></a><span data-ttu-id="673a4-102">Definizione di tipo anonimo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="673a4-102">Anonymous Type Definition (Visual Basic)</span></span>

<span data-ttu-id="673a4-103">In risposta alla dichiarazione di un'istanza di un tipo anonimo, il compilatore crea una nuova definizione di classe che contiene le proprietà specificate per il tipo.</span><span class="sxs-lookup"><span data-stu-id="673a4-103">In response to the declaration of an instance of an anonymous type, the compiler creates a new class definition that contains the specified properties for the type.</span></span>

## <a name="compiler-generated-code"></a><span data-ttu-id="673a4-104">Codice generato dal compilatore</span><span class="sxs-lookup"><span data-stu-id="673a4-104">Compiler-Generated Code</span></span>

<span data-ttu-id="673a4-105">Per la seguente definizione di `product`, il compilatore crea una nuova definizione di classe che contiene le proprietà `Name`, `Price`, e `OnHand`.</span><span class="sxs-lookup"><span data-stu-id="673a4-105">For the following definition of `product`, the compiler creates a new class definition that contains properties `Name`, `Price`, and `OnHand`.</span></span>

[!code-vb[VbVbalrAnonymousTypes#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#25)]

<span data-ttu-id="673a4-106">La definizione della classe contiene le definizioni delle proprietà simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="673a4-106">The class definition contains property definitions similar to the following.</span></span> <span data-ttu-id="673a4-107">Si noti che non vi è alcun `Set` metodo per la proprietà chiave.</span><span class="sxs-lookup"><span data-stu-id="673a4-107">Notice that there is no `Set` method for the key properties.</span></span> <span data-ttu-id="673a4-108">I valori delle proprietà di chiave sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="673a4-108">The values of key properties are read-only.</span></span>

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

<span data-ttu-id="673a4-109">Inoltre, le definizioni di tipo anonimo contengono un costruttore predefinito.</span><span class="sxs-lookup"><span data-stu-id="673a4-109">In addition, anonymous type definitions contain a default constructor.</span></span> <span data-ttu-id="673a4-110">I costruttori che richiedono parametri non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="673a4-110">Constructors that require parameters are not permitted.</span></span>

<span data-ttu-id="673a4-111">Se una dichiarazione di tipo anonimo contiene almeno una proprietà chiave, la definizione del tipo esegue l'override di tre membri ereditati da <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, e <xref:System.Object.ToString%2A>.</span><span class="sxs-lookup"><span data-stu-id="673a4-111">If an anonymous type declaration contains at least one key property, the type definition overrides three members inherited from <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="673a4-112">Se nessuna proprietà chiave viene dichiarata, solo <xref:System.Object.ToString%2A> viene sottoposto a override.</span><span class="sxs-lookup"><span data-stu-id="673a4-112">If no key properties are declared, only <xref:System.Object.ToString%2A> is overridden.</span></span> <span data-ttu-id="673a4-113">Le sostituzioni offrono le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="673a4-113">The overrides provide the following functionality:</span></span>

- <span data-ttu-id="673a4-114">`Equals` Restituisce `True` se due istanze di tipo anonimo sono la stessa istanza o se soddisfano le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="673a4-114">`Equals` returns `True` if two anonymous type instances are the same instance, or if they meet the following conditions:</span></span>

  - <span data-ttu-id="673a4-115">Hanno lo stesso numero di proprietà.</span><span class="sxs-lookup"><span data-stu-id="673a4-115">They have the same number of properties.</span></span>

  - <span data-ttu-id="673a4-116">Le proprietà vengono dichiarate nello stesso ordine, con gli stessi nomi e gli stessi tipi dedotti.</span><span class="sxs-lookup"><span data-stu-id="673a4-116">The properties are declared in the same order, with the same names and the same inferred types.</span></span> <span data-ttu-id="673a4-117">I confronti tra nomi non sono tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="673a4-117">Name comparisons are not case-sensitive.</span></span>

  - <span data-ttu-id="673a4-118">Almeno una delle proprietà è una proprietà chiave e il `Key` viene applicata la parola chiave per le stesse proprietà.</span><span class="sxs-lookup"><span data-stu-id="673a4-118">At least one of the properties is a key property, and the `Key` keyword is applied to the same properties.</span></span>

  - <span data-ttu-id="673a4-119">Confronto tra ogni coppia corrispondente di proprietà di chiave restituisce `True`.</span><span class="sxs-lookup"><span data-stu-id="673a4-119">Comparison of each corresponding pair of key properties returns `True`.</span></span>

    <span data-ttu-id="673a4-120">Ad esempio, negli esempi seguenti `Equals` restituisce `True` solo per `employee01` e `employee08`.</span><span class="sxs-lookup"><span data-stu-id="673a4-120">For example, in the following examples, `Equals` returns `True` only for `employee01` and `employee08`.</span></span> <span data-ttu-id="673a4-121">Il commento prima di ogni riga specifica il motivo per cui la nuova istanza non corrisponde `employee01`.</span><span class="sxs-lookup"><span data-stu-id="673a4-121">The comment before each line specifies the reason why the new instance does not match `employee01`.</span></span>

    [!code-vb[VbVbalrAnonymousTypes#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#24)]

- <span data-ttu-id="673a4-122">`GetHashcode` fornisce un algoritmo GetHashCode univoco in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="673a4-122">`GetHashcode` provides an appropriately unique GetHashCode algorithm.</span></span> <span data-ttu-id="673a4-123">L'algoritmo Usa solo le proprietà della chiave per calcolare il codice hash.</span><span class="sxs-lookup"><span data-stu-id="673a4-123">The algorithm uses only the key properties to compute the hash code.</span></span>

- <span data-ttu-id="673a4-124">`ToString` Restituisce una stringa concatenata dei valori delle proprietà, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="673a4-124">`ToString` returns a string of concatenated property values, as shown in the following example.</span></span> <span data-ttu-id="673a4-125">Sono incluse sia chiave e le proprietà non chiave.</span><span class="sxs-lookup"><span data-stu-id="673a4-125">Both key and non-key properties are included.</span></span>

  [!code-vb[VbVbalrAnonymousTypes#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#29)]

<span data-ttu-id="673a4-126">Proprietà denominate in modo esplicito di un tipo anonimo non è in conflitto con questi metodi generati.</span><span class="sxs-lookup"><span data-stu-id="673a4-126">Explicitly named properties of an anonymous type cannot conflict with these generated methods.</span></span> <span data-ttu-id="673a4-127">Vale a dire, non è possibile usare `.Equals`, `.GetHashCode`, o `.ToString` per assegnare un nome di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="673a4-127">That is, you cannot use `.Equals`, `.GetHashCode`, or `.ToString` to name a property.</span></span>

<span data-ttu-id="673a4-128">Le definizioni di tipo anonimo che include almeno una proprietà chiave implementano anche il <xref:System.IEquatable%601?displayProperty=nameWithType> interfaccia, in cui `T` è il tipo del tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="673a4-128">Anonymous type definitions that include at least one key property also implement the <xref:System.IEquatable%601?displayProperty=nameWithType> interface, where `T` is the type of the anonymous type.</span></span>

> [!NOTE]
> <span data-ttu-id="673a4-129">Dichiarazioni di tipo anonimo creare lo stesso tipo anonimo solo se si verificano nello stesso assembly, le relative proprietà hanno gli stessi nomi e gli stessi tipi dedotti, nello stesso ordine in cui sono dichiarate le proprietà e le stesse proprietà vengono contrassegnate come proprietà chiave.</span><span class="sxs-lookup"><span data-stu-id="673a4-129">Anonymous type declarations create the same anonymous type only if they occur in the same assembly, their properties have the same names and the same inferred types, the properties are declared in the same order, and the same properties are marked as key properties.</span></span>

## <a name="see-also"></a><span data-ttu-id="673a4-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="673a4-130">See also</span></span>

- [<span data-ttu-id="673a4-131">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="673a4-131">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="673a4-132">Procedura: Dedurre i nomi delle proprietà e i tipi nelle dichiarazioni di tipo anonimo</span><span class="sxs-lookup"><span data-stu-id="673a4-132">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
