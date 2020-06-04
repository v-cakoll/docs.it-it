---
title: 'Procedura: determinare a quale tipo fa riferimento una variabile oggetto'
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: d3224000f5958a8619e38c4d2f6dc5dbb275ad45
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410490"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a><span data-ttu-id="d6427-102">Procedura: determinare a quale tipo fa riferimento una variabile oggetto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6427-102">How to: Determine What Type an Object Variable Refers To (Visual Basic)</span></span>

<span data-ttu-id="d6427-103">Una variabile oggetto contiene un puntatore ai dati archiviati altrove.</span><span class="sxs-lookup"><span data-stu-id="d6427-103">An object variable contains a pointer to data that is stored elsewhere.</span></span> <span data-ttu-id="d6427-104">Il tipo di dati può essere modificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d6427-104">The type of that data can change during run time.</span></span> <span data-ttu-id="d6427-105">In qualsiasi momento, è possibile utilizzare il <xref:System.Type.GetTypeCode%2A> metodo per determinare il tipo in fase di esecuzione corrente o l' [operatore typeof](../../../language-reference/operators/typeof-operator.md) per verificare se il tipo di runtime corrente è compatibile con un tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="d6427-105">At any moment, you can use the <xref:System.Type.GetTypeCode%2A> method to determine the current run-time type, or the [TypeOf Operator](../../../language-reference/operators/typeof-operator.md) to find out if the current run-time type is compatible with a specified type.</span></span>

### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a><span data-ttu-id="d6427-106">Per determinare il tipo esatto a cui fa attualmente riferimento una variabile oggetto</span><span class="sxs-lookup"><span data-stu-id="d6427-106">To determine the exact type an object variable currently refers to</span></span>

1. <span data-ttu-id="d6427-107">Nella variabile oggetto chiamare il <xref:System.Object.GetType%2A> metodo per recuperare un <xref:System.Type?displayProperty=nameWithType> oggetto.</span><span class="sxs-lookup"><span data-stu-id="d6427-107">On the object variable, call the <xref:System.Object.GetType%2A> method to retrieve a <xref:System.Type?displayProperty=nameWithType> object.</span></span>

    ```vb
    Dim myObject As Object
    myObject.GetType()
    ```

2. <span data-ttu-id="d6427-108">Nella <xref:System.Type?displayProperty=nameWithType> classe chiamare il metodo Shared <xref:System.Type.GetTypeCode%2A> per recuperare il valore di <xref:System.TypeCode> enumerazione per il tipo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="d6427-108">On the <xref:System.Type?displayProperty=nameWithType> class, call the shared method <xref:System.Type.GetTypeCode%2A> to retrieve the <xref:System.TypeCode> enumeration value for the object's type.</span></span>

    ```vb
    Dim myObject As Object
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())
    MsgBox("myObject currently has type code " & CStr(datTyp))
    ```

    <span data-ttu-id="d6427-109">È possibile testare il <xref:System.TypeCode> valore di enumerazione rispetto a qualsiasi membro di enumerazione di interesse, ad esempio `Double` .</span><span class="sxs-lookup"><span data-stu-id="d6427-109">You can test the <xref:System.TypeCode> enumeration value against whichever enumeration members are of interest, such as `Double`.</span></span>

### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a><span data-ttu-id="d6427-110">Per determinare se il tipo di una variabile oggetto è compatibile con un tipo specificato</span><span class="sxs-lookup"><span data-stu-id="d6427-110">To determine whether an object variable's type is compatible with a specified type</span></span>

- <span data-ttu-id="d6427-111">Usare l' `TypeOf` operatore in combinazione con l' [operatore is](../../../language-reference/operators/is-operator.md) per testare l'oggetto con un' `TypeOf` espressione... `Is` .</span><span class="sxs-lookup"><span data-stu-id="d6427-111">Use the `TypeOf` operator in combination with the [Is Operator](../../../language-reference/operators/is-operator.md) to test the object with a `TypeOf`...`Is` expression.</span></span>

    ```vb
    If TypeOf objA Is System.Windows.Forms.Control Then
        MsgBox("objA is compatible with the Control class")
    End If
    ```

    <span data-ttu-id="d6427-112">L' `TypeOf` espressione... `Is` restituisce `True` se il tipo di runtime dell'oggetto è compatibile con il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="d6427-112">The `TypeOf`...`Is` expression returns `True` if the object's run-time type is compatible with the specified type.</span></span>

    <span data-ttu-id="d6427-113">Il criterio per la compatibilità dipende dal fatto che il tipo specificato sia una classe, una struttura o un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d6427-113">The criterion for compatibility depends on whether the specified type is a class, structure, or interface.</span></span> <span data-ttu-id="d6427-114">In generale, i tipi sono compatibili se l'oggetto è dello stesso tipo di, eredita da o implementa il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="d6427-114">In general, the types are compatible if the object is of the same type as, inherits from, or implements the specified type.</span></span> <span data-ttu-id="d6427-115">Per ulteriori informazioni, vedere [operatore typeof](../../../language-reference/operators/typeof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="d6427-115">For more information, see [TypeOf Operator](../../../language-reference/operators/typeof-operator.md).</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="d6427-116">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="d6427-116">Compile the code</span></span>

<span data-ttu-id="d6427-117">Si noti che il tipo specificato non può essere una variabile o un'espressione.</span><span class="sxs-lookup"><span data-stu-id="d6427-117">Note that the specified type cannot be a variable or expression.</span></span> <span data-ttu-id="d6427-118">Deve corrispondere al nome di un tipo definito, ad esempio una classe, una struttura o un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d6427-118">It must be the name of a defined type, such as a class, structure, or interface.</span></span> <span data-ttu-id="d6427-119">Sono inclusi i tipi intrinseci, ad esempio `Integer` e `String` .</span><span class="sxs-lookup"><span data-stu-id="d6427-119">This includes intrinsic types such as `Integer` and `String`.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6427-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6427-120">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [<span data-ttu-id="d6427-121">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="d6427-121">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="d6427-122">Valori di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="d6427-122">Object Variable Values</span></span>](object-variable-values.md)
- [<span data-ttu-id="d6427-123">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="d6427-123">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
