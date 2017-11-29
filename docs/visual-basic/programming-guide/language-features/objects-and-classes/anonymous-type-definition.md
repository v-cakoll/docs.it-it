---
title: Definizione di tipo anonimo (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8b5b7eba55d719c1482b7224ecffc78b776feb00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="anonymous-type-definition-visual-basic"></a><span data-ttu-id="454d8-102">Definizione di tipo anonimo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="454d8-102">Anonymous Type Definition (Visual Basic)</span></span>
<span data-ttu-id="454d8-103">In risposta alla dichiarazione di un'istanza di un tipo anonimo, il compilatore crea una nuova definizione di classe che contiene le proprietà per il tipo specificate.</span><span class="sxs-lookup"><span data-stu-id="454d8-103">In response to the declaration of an instance of an anonymous type, the compiler creates a new class definition that contains the specified properties for the type.</span></span>  
  
## <a name="compiler-generated-code"></a><span data-ttu-id="454d8-104">Codice generato dal compilatore</span><span class="sxs-lookup"><span data-stu-id="454d8-104">Compiler-Generated Code</span></span>  
 <span data-ttu-id="454d8-105">Per la seguente definizione di `product`, il compilatore crea una nuova definizione di classe contenente proprietà `Name`, `Price`, e `OnHand`.</span><span class="sxs-lookup"><span data-stu-id="454d8-105">For the following definition of `product`, the compiler creates a new class definition that contains properties `Name`, `Price`, and `OnHand`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#25](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_1.vb)]  
  
 <span data-ttu-id="454d8-106">La definizione della classe contiene le definizioni di proprietà simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="454d8-106">The class definition contains property definitions similar to the following.</span></span> <span data-ttu-id="454d8-107">Si noti che non vi è alcun `Set` metodo per la proprietà chiave.</span><span class="sxs-lookup"><span data-stu-id="454d8-107">Notice that there is no `Set` method for the key properties.</span></span> <span data-ttu-id="454d8-108">I valori delle proprietà chiave sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="454d8-108">The values of key properties are read-only.</span></span>  
  
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
  
 <span data-ttu-id="454d8-109">Inoltre, le definizioni di tipo anonimo contengono un costruttore predefinito.</span><span class="sxs-lookup"><span data-stu-id="454d8-109">In addition, anonymous type definitions contain a default constructor.</span></span> <span data-ttu-id="454d8-110">Non sono consentiti costruttori che richiedono parametri.</span><span class="sxs-lookup"><span data-stu-id="454d8-110">Constructors that require parameters are not permitted.</span></span>  
  
 <span data-ttu-id="454d8-111">Se una dichiarazione di tipo anonimo contiene almeno una proprietà chiave, la definizione del tipo esegue l'override di tre membri ereditati da <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, e <xref:System.Object.ToString%2A>.</span><span class="sxs-lookup"><span data-stu-id="454d8-111">If an anonymous type declaration contains at least one key property, the type definition overrides three members inherited from <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="454d8-112">Se viene dichiarata alcuna proprietà chiave, solo <xref:System.Object.ToString%2A> viene sottoposto a override.</span><span class="sxs-lookup"><span data-stu-id="454d8-112">If no key properties are declared, only <xref:System.Object.ToString%2A> is overridden.</span></span> <span data-ttu-id="454d8-113">Le sostituzioni forniscono le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="454d8-113">The overrides provide the following functionality:</span></span>  
  
-   <span data-ttu-id="454d8-114">`Equals`Restituisce `True` se due istanze di tipo anonimo sono la stessa istanza o che soddisfano le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="454d8-114">`Equals` returns `True` if two anonymous type instances are the same instance, or if they meet the following conditions:</span></span>  
  
    -   <span data-ttu-id="454d8-115">Hanno lo stesso numero di proprietà.</span><span class="sxs-lookup"><span data-stu-id="454d8-115">They have the same number of properties.</span></span>  
  
    -   <span data-ttu-id="454d8-116">Le proprietà vengono dichiarate nello stesso ordine, con gli stessi nomi e gli stessi tipi dedotti.</span><span class="sxs-lookup"><span data-stu-id="454d8-116">The properties are declared in the same order, with the same names and the same inferred types.</span></span> <span data-ttu-id="454d8-117">Confronti tra nomi non è rilevanti.</span><span class="sxs-lookup"><span data-stu-id="454d8-117">Name comparisons are not case-sensitive.</span></span>  
  
    -   <span data-ttu-id="454d8-118">Almeno una delle proprietà è una proprietà chiave e `Key` (parola chiave) viene applicato alle stesse proprietà.</span><span class="sxs-lookup"><span data-stu-id="454d8-118">At least one of the properties is a key property, and the `Key` keyword is applied to the same properties.</span></span>  
  
    -   <span data-ttu-id="454d8-119">Confronto tra ogni coppia corrispondente di proprietà chiave restituisce `True`.</span><span class="sxs-lookup"><span data-stu-id="454d8-119">Comparison of each corresponding pair of key properties returns `True`.</span></span>  
  
     <span data-ttu-id="454d8-120">Ad esempio, negli esempi seguenti, `Equals` restituisce `True` solo per `employee01` e `employee08`.</span><span class="sxs-lookup"><span data-stu-id="454d8-120">For example, in the following examples, `Equals` returns `True` only for `employee01` and `employee08`.</span></span> <span data-ttu-id="454d8-121">Il commento prima di ogni riga specifica il motivo per cui corrisponde la nuova istanza `employee01`.</span><span class="sxs-lookup"><span data-stu-id="454d8-121">The comment before each line specifies the reason why the new instance does not match `employee01`.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#24](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_2.vb)]  
  
-   <span data-ttu-id="454d8-122">`GetHashcode`fornisce un algoritmo di GetHashCode adeguatamente univoco.</span><span class="sxs-lookup"><span data-stu-id="454d8-122">`GetHashcode` provides an appropriately unique GetHashCode algorithm.</span></span> <span data-ttu-id="454d8-123">L'algoritmo utilizza solo le proprietà chiave per calcolare il codice hash.</span><span class="sxs-lookup"><span data-stu-id="454d8-123">The algorithm uses only the key properties to compute the hash code.</span></span>  
  
-   <span data-ttu-id="454d8-124">`ToString`Restituisce una stringa concatenate dei valori delle proprietà, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="454d8-124">`ToString` returns a string of concatenated property values, as shown in the following example.</span></span> <span data-ttu-id="454d8-125">Chiave e le proprietà non chiave sono inclusione.</span><span class="sxs-lookup"><span data-stu-id="454d8-125">Both key and non-key properties are included.</span></span>  
  
     [!code-vb[VbVbalrAnonymousTypes#29](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-type-definition_3.vb)]  
  
 <span data-ttu-id="454d8-126">Proprietà denominate in modo esplicito di un tipo anonimo non è in conflitto con questi metodi generati.</span><span class="sxs-lookup"><span data-stu-id="454d8-126">Explicitly named properties of an anonymous type cannot conflict with these generated methods.</span></span> <span data-ttu-id="454d8-127">Ovvero, non è possibile utilizzare `.Equals`, `.GetHashCode`, o `.ToString` per assegnare un nome di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="454d8-127">That is, you cannot use `.Equals`, `.GetHashCode`, or `.ToString` to name a property.</span></span>  
  
 <span data-ttu-id="454d8-128">Definizioni di tipo anonimo che comprendono almeno una proprietà chiave implementano anche il <xref:System.IEquatable%601?displayProperty=nameWithType> interfaccia, in cui `T` è il tipo del tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="454d8-128">Anonymous type definitions that include at least one key property also implement the <xref:System.IEquatable%601?displayProperty=nameWithType> interface, where `T` is the type of the anonymous type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="454d8-129">Dichiarazioni di tipo anonimo creare lo stesso tipo anonimo solo se si verificano nello stesso assembly, le relative proprietà hanno gli stessi nomi e gli stessi tipi dedotti, nello stesso ordine in cui sono dichiarate le proprietà e le stesse proprietà sono contrassegnate come proprietà chiave.</span><span class="sxs-lookup"><span data-stu-id="454d8-129">Anonymous type declarations create the same anonymous type only if they occur in the same assembly, their properties have the same names and the same inferred types, the properties are declared in the same order, and the same properties are marked as key properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="454d8-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="454d8-130">See Also</span></span>  
 [<span data-ttu-id="454d8-131">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="454d8-131">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [<span data-ttu-id="454d8-132">Procedura: Dedurre tipi e nomi di proprietà nelle dichiarazioni di tipo anonimo</span><span class="sxs-lookup"><span data-stu-id="454d8-132">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
