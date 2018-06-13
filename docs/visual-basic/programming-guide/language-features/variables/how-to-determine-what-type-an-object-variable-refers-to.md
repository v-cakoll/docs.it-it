---
title: 'Procedura: determinare a quale tipo fa riferimento una variabile oggetto (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: 0dfd4ed87b65f536802ae71cbc3de41e1c4f83af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651314"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a><span data-ttu-id="3aae5-102">Procedura: determinare a quale tipo fa riferimento una variabile oggetto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3aae5-102">How to: Determine What Type an Object Variable Refers To (Visual Basic)</span></span>
<span data-ttu-id="3aae5-103">Una variabile oggetto contiene un puntatore a dati archiviati in un' posizione.</span><span class="sxs-lookup"><span data-stu-id="3aae5-103">An object variable contains a pointer to data that is stored elsewhere.</span></span> <span data-ttu-id="3aae5-104">Il tipo di dati può cambiare in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3aae5-104">The type of that data can change during run time.</span></span> <span data-ttu-id="3aae5-105">In qualsiasi momento, è possibile utilizzare il <xref:System.Type.GetTypeCode%2A> metodo per determinare il tipo in fase di esecuzione corrente, o [operatore TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md) per determinare se il tipo in fase di esecuzione è compatibile con un tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="3aae5-105">At any moment, you can use the <xref:System.Type.GetTypeCode%2A> method to determine the current run-time type, or the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to find out if the current run-time type is compatible with a specified type.</span></span>  
  
### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a><span data-ttu-id="3aae5-106">Per determinare che il tipo esatto una variabile oggetto attualmente fa riferimento a</span><span class="sxs-lookup"><span data-stu-id="3aae5-106">To determine the exact type an object variable currently refers to</span></span>  
  
1.  <span data-ttu-id="3aae5-107">La variabile oggetto, chiamare il <xref:System.Object.GetType%2A> metodo per recuperare un <xref:System.Type?displayProperty=nameWithType> oggetto.</span><span class="sxs-lookup"><span data-stu-id="3aae5-107">On the object variable, call the <xref:System.Object.GetType%2A> method to retrieve a <xref:System.Type?displayProperty=nameWithType> object.</span></span>  
  
    ```  
    Dim myObject As Object  
    myObject.GetType()  
    ```  
  
2.  <span data-ttu-id="3aae5-108">Nel <xref:System.Type?displayProperty=nameWithType> classe, chiamare il metodo condiviso <xref:System.Type.GetTypeCode%2A> per recuperare il <xref:System.TypeCode> valore di enumerazione per il tipo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="3aae5-108">On the <xref:System.Type?displayProperty=nameWithType> class, call the shared method <xref:System.Type.GetTypeCode%2A> to retrieve the <xref:System.TypeCode> enumeration value for the object's type.</span></span>  
  
    ```  
    Dim myObject As Object  
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())  
    MsgBox("myObject currently has type code " & CStr(datTyp))  
    ```  
  
     <span data-ttu-id="3aae5-109">È possibile testare il <xref:System.TypeCode> il valore di enumerazione rispetto a un qualsiasi membro di enumerazione di interesse, ad esempio `Double`.</span><span class="sxs-lookup"><span data-stu-id="3aae5-109">You can test the <xref:System.TypeCode> enumeration value against whichever enumeration members are of interest, such as `Double`.</span></span>  
  
### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a><span data-ttu-id="3aae5-110">Per determinare se un oggetto tipo di variabile è compatibile con un tipo specificato</span><span class="sxs-lookup"><span data-stu-id="3aae5-110">To determine whether an object variable's type is compatible with a specified type</span></span>  
  
-   <span data-ttu-id="3aae5-111">Utilizzare il `TypeOf` operatore in combinazione con il [operatore Is](../../../../visual-basic/language-reference/operators/is-operator.md) per testare l'oggetto con un `TypeOf`... `Is` espressione.</span><span class="sxs-lookup"><span data-stu-id="3aae5-111">Use the `TypeOf` operator in combination with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) to test the object with a `TypeOf`...`Is` expression.</span></span>  
  
    ```  
    If TypeOf objA Is System.Windows.Forms.Control Then  
        MsgBox("objA is compatible with the Control class")  
    End If  
    ```  
  
     <span data-ttu-id="3aae5-112">Il `TypeOf`... `Is` restituisce `True` se l'oggetto della fase di esecuzione tipo è compatibile con il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="3aae5-112">The `TypeOf`...`Is` expression returns `True` if the object's run-time type is compatible with the specified type.</span></span>  
  
     <span data-ttu-id="3aae5-113">Il criterio per la compatibilità varia a seconda che il tipo specificato una classe, struttura o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="3aae5-113">The criterion for compatibility depends on whether the specified type is a class, structure, or interface.</span></span> <span data-ttu-id="3aae5-114">In generale, i tipi sono compatibili, se l'oggetto è dello stesso tipo, eredita da o implementa il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="3aae5-114">In general, the types are compatible if the object is of the same type as, inherits from, or implements the specified type.</span></span> <span data-ttu-id="3aae5-115">Per ulteriori informazioni, vedere [operatore TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="3aae5-115">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3aae5-116">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="3aae5-116">Compiling the Code</span></span>  
 <span data-ttu-id="3aae5-117">Si noti che il tipo specificato non può essere una variabile o espressione.</span><span class="sxs-lookup"><span data-stu-id="3aae5-117">Note that the specified type cannot be a variable or expression.</span></span> <span data-ttu-id="3aae5-118">Deve essere il nome di un tipo definito, ad esempio una classe, struttura o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="3aae5-118">It must be the name of a defined type, such as a class, structure, or interface.</span></span> <span data-ttu-id="3aae5-119">Inclusi i tipi intrinseci, ad esempio `Integer` e `String`.</span><span class="sxs-lookup"><span data-stu-id="3aae5-119">This includes intrinsic types such as `Integer` and `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aae5-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3aae5-120">See Also</span></span>  
 <xref:System.Object.GetType%2A>  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Type.GetTypeCode%2A>  
 <xref:System.TypeCode>  
 [<span data-ttu-id="3aae5-121">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="3aae5-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="3aae5-122">Valori di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="3aae5-122">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [<span data-ttu-id="3aae5-123">Tipo di dati Object</span><span class="sxs-lookup"><span data-stu-id="3aae5-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
