---
title: 'Procedura: determinare a quale tipo fa riferimento una variabile oggetto'
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: b3778a170759f685db78e7dcde219138196f9eca
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344192"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a><span data-ttu-id="333ed-102">Procedura: determinare a quale tipo fa riferimento una variabile oggetto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="333ed-102">How to: Determine What Type an Object Variable Refers To (Visual Basic)</span></span>

<span data-ttu-id="333ed-103">Una variabile oggetto contiene un puntatore ai dati archiviati altrove.</span><span class="sxs-lookup"><span data-stu-id="333ed-103">An object variable contains a pointer to data that is stored elsewhere.</span></span> <span data-ttu-id="333ed-104">Il tipo di dati può essere modificato in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="333ed-104">The type of that data can change during run time.</span></span> <span data-ttu-id="333ed-105">In qualsiasi momento, è possibile utilizzare il metodo <xref:System.Type.GetTypeCode%2A> per determinare il tipo in fase di esecuzione corrente o l' [operatore typeof](../../../../visual-basic/language-reference/operators/typeof-operator.md) per verificare se il tipo di runtime corrente è compatibile con un tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="333ed-105">At any moment, you can use the <xref:System.Type.GetTypeCode%2A> method to determine the current run-time type, or the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to find out if the current run-time type is compatible with a specified type.</span></span>

### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a><span data-ttu-id="333ed-106">Per determinare il tipo esatto a cui fa attualmente riferimento una variabile oggetto</span><span class="sxs-lookup"><span data-stu-id="333ed-106">To determine the exact type an object variable currently refers to</span></span>

1. <span data-ttu-id="333ed-107">Nella variabile oggetto chiamare il metodo <xref:System.Object.GetType%2A> per recuperare un oggetto <xref:System.Type?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="333ed-107">On the object variable, call the <xref:System.Object.GetType%2A> method to retrieve a <xref:System.Type?displayProperty=nameWithType> object.</span></span>

    ```vb
    Dim myObject As Object
    myObject.GetType()
    ```

2. <span data-ttu-id="333ed-108">Nella classe <xref:System.Type?displayProperty=nameWithType> chiamare il metodo Shared <xref:System.Type.GetTypeCode%2A> per recuperare il <xref:System.TypeCode> valore di enumerazione per il tipo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="333ed-108">On the <xref:System.Type?displayProperty=nameWithType> class, call the shared method <xref:System.Type.GetTypeCode%2A> to retrieve the <xref:System.TypeCode> enumeration value for the object's type.</span></span>

    ```vb
    Dim myObject As Object
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())
    MsgBox("myObject currently has type code " & CStr(datTyp))
    ```

    <span data-ttu-id="333ed-109">È possibile testare il valore di enumerazione <xref:System.TypeCode> rispetto a qualsiasi membro di enumerazione di interesse, ad esempio `Double`.</span><span class="sxs-lookup"><span data-stu-id="333ed-109">You can test the <xref:System.TypeCode> enumeration value against whichever enumeration members are of interest, such as `Double`.</span></span>

### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a><span data-ttu-id="333ed-110">Per determinare se il tipo di una variabile oggetto è compatibile con un tipo specificato</span><span class="sxs-lookup"><span data-stu-id="333ed-110">To determine whether an object variable's type is compatible with a specified type</span></span>

- <span data-ttu-id="333ed-111">Utilizzare l'operatore `TypeOf` in combinazione con l' [operatore is](../../../../visual-basic/language-reference/operators/is-operator.md) per testare l'oggetto con un'espressione `TypeOf`...`Is`.</span><span class="sxs-lookup"><span data-stu-id="333ed-111">Use the `TypeOf` operator in combination with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) to test the object with a `TypeOf`...`Is` expression.</span></span>

    ```vb
    If TypeOf objA Is System.Windows.Forms.Control Then
        MsgBox("objA is compatible with the Control class")
    End If
    ```

    <span data-ttu-id="333ed-112">L'espressione `TypeOf`...`Is` restituisce `True` se il tipo di runtime dell'oggetto è compatibile con il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="333ed-112">The `TypeOf`...`Is` expression returns `True` if the object's run-time type is compatible with the specified type.</span></span>

    <span data-ttu-id="333ed-113">Il criterio per la compatibilità dipende dal fatto che il tipo specificato sia una classe, una struttura o un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="333ed-113">The criterion for compatibility depends on whether the specified type is a class, structure, or interface.</span></span> <span data-ttu-id="333ed-114">In generale, i tipi sono compatibili se l'oggetto è dello stesso tipo di, eredita da o implementa il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="333ed-114">In general, the types are compatible if the object is of the same type as, inherits from, or implements the specified type.</span></span> <span data-ttu-id="333ed-115">Per ulteriori informazioni, vedere [operatore typeof](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="333ed-115">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="333ed-116">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="333ed-116">Compile the code</span></span>

<span data-ttu-id="333ed-117">Si noti che il tipo specificato non può essere una variabile o un'espressione.</span><span class="sxs-lookup"><span data-stu-id="333ed-117">Note that the specified type cannot be a variable or expression.</span></span> <span data-ttu-id="333ed-118">Deve corrispondere al nome di un tipo definito, ad esempio una classe, una struttura o un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="333ed-118">It must be the name of a defined type, such as a class, structure, or interface.</span></span> <span data-ttu-id="333ed-119">Sono inclusi i tipi intrinseci, ad esempio `Integer` e `String`.</span><span class="sxs-lookup"><span data-stu-id="333ed-119">This includes intrinsic types such as `Integer` and `String`.</span></span>

## <a name="see-also"></a><span data-ttu-id="333ed-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="333ed-120">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [<span data-ttu-id="333ed-121">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="333ed-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="333ed-122">Valori di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="333ed-122">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="333ed-123">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="333ed-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
