---
title: 'Procedura: Determinare a quale tipo fa riferimento una variabile oggetto (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: 6499dfce880cc9ce16e5d77887afc0598692f48e
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59342869"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a><span data-ttu-id="9a47c-102">Procedura: Determinare a quale tipo fa riferimento una variabile oggetto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a47c-102">How to: Determine What Type an Object Variable Refers To (Visual Basic)</span></span>
<span data-ttu-id="9a47c-103">Una variabile oggetto contiene un puntatore ai dati archiviati in un' posizione.</span><span class="sxs-lookup"><span data-stu-id="9a47c-103">An object variable contains a pointer to data that is stored elsewhere.</span></span> <span data-ttu-id="9a47c-104">Il tipo di dati può modificare durante la fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9a47c-104">The type of that data can change during run time.</span></span> <span data-ttu-id="9a47c-105">In qualsiasi momento, è possibile usare la <xref:System.Type.GetTypeCode%2A> metodo per determinare il tipo di runtime corrente, o il [operatore TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md) per determinare se il tipo in fase di esecuzione è compatibile con un tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="9a47c-105">At any moment, you can use the <xref:System.Type.GetTypeCode%2A> method to determine the current run-time type, or the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to find out if the current run-time type is compatible with a specified type.</span></span>  
  
### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a><span data-ttu-id="9a47c-106">Per determinare che il tipo esatto una variabile oggetto attualmente fa riferimento a</span><span class="sxs-lookup"><span data-stu-id="9a47c-106">To determine the exact type an object variable currently refers to</span></span>  
  
1. <span data-ttu-id="9a47c-107">La variabile oggetto, chiamare il <xref:System.Object.GetType%2A> metodo per recuperare un <xref:System.Type?displayProperty=nameWithType> oggetto.</span><span class="sxs-lookup"><span data-stu-id="9a47c-107">On the object variable, call the <xref:System.Object.GetType%2A> method to retrieve a <xref:System.Type?displayProperty=nameWithType> object.</span></span>  
  
    ```  
    Dim myObject As Object  
    myObject.GetType()  
    ```  
  
2. <span data-ttu-id="9a47c-108">Nel <xref:System.Type?displayProperty=nameWithType> classe, chiamare il metodo condiviso <xref:System.Type.GetTypeCode%2A> per recuperare il <xref:System.TypeCode> valore di enumerazione per il tipo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="9a47c-108">On the <xref:System.Type?displayProperty=nameWithType> class, call the shared method <xref:System.Type.GetTypeCode%2A> to retrieve the <xref:System.TypeCode> enumeration value for the object's type.</span></span>  
  
    ```  
    Dim myObject As Object  
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())  
    MsgBox("myObject currently has type code " & CStr(datTyp))  
    ```  
  
     <span data-ttu-id="9a47c-109">È possibile testare il <xref:System.TypeCode> valore dell'enumerazione su un qualsiasi membro di enumerazione è di interesse, ad esempio `Double`.</span><span class="sxs-lookup"><span data-stu-id="9a47c-109">You can test the <xref:System.TypeCode> enumeration value against whichever enumeration members are of interest, such as `Double`.</span></span>  
  
### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a><span data-ttu-id="9a47c-110">Per determinare se un oggetto tipo di variabile è compatibile con un tipo specificato</span><span class="sxs-lookup"><span data-stu-id="9a47c-110">To determine whether an object variable's type is compatible with a specified type</span></span>  
  
-   <span data-ttu-id="9a47c-111">Usare la `TypeOf` operatore in combinazione con il [operatore Is](../../../../visual-basic/language-reference/operators/is-operator.md) per testare l'oggetto con un `TypeOf`... `Is` espressione.</span><span class="sxs-lookup"><span data-stu-id="9a47c-111">Use the `TypeOf` operator in combination with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) to test the object with a `TypeOf`...`Is` expression.</span></span>  
  
    ```  
    If TypeOf objA Is System.Windows.Forms.Control Then  
        MsgBox("objA is compatible with the Control class")  
    End If  
    ```  
  
     <span data-ttu-id="9a47c-112">Il `TypeOf`... `Is` espressione restituisce `True` se l'oggetto della fase di esecuzione tipo è compatibile con il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="9a47c-112">The `TypeOf`...`Is` expression returns `True` if the object's run-time type is compatible with the specified type.</span></span>  
  
     <span data-ttu-id="9a47c-113">Il criterio per la compatibilità dipende dal fatto che il tipo specificato è una classe, struttura o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="9a47c-113">The criterion for compatibility depends on whether the specified type is a class, structure, or interface.</span></span> <span data-ttu-id="9a47c-114">In generale, i tipi sono compatibili se l'oggetto è dello stesso tipo, eredita o implementa il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="9a47c-114">In general, the types are compatible if the object is of the same type as, inherits from, or implements the specified type.</span></span> <span data-ttu-id="9a47c-115">Per altre informazioni, vedere [operatore TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="9a47c-115">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9a47c-116">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="9a47c-116">Compiling the Code</span></span>  
 <span data-ttu-id="9a47c-117">Si noti che il tipo specificato non può essere una variabile o espressione.</span><span class="sxs-lookup"><span data-stu-id="9a47c-117">Note that the specified type cannot be a variable or expression.</span></span> <span data-ttu-id="9a47c-118">Deve essere il nome di un tipo definito, ad esempio una classe, struttura o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="9a47c-118">It must be the name of a defined type, such as a class, structure, or interface.</span></span> <span data-ttu-id="9a47c-119">Questo include, ad esempio tipi intrinseci `Integer` e `String`.</span><span class="sxs-lookup"><span data-stu-id="9a47c-119">This includes intrinsic types such as `Integer` and `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a47c-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a47c-120">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [<span data-ttu-id="9a47c-121">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="9a47c-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="9a47c-122">Valori di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="9a47c-122">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="9a47c-123">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="9a47c-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
