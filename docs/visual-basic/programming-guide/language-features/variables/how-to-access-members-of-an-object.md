---
title: 'Procedura: accedere ai membri di un oggetto'
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: 2826a3c98b9f19b08cc943d0f67cdd34ac90f526
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410542"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a><span data-ttu-id="4dc50-102">Procedura: accedere ai membri di un oggetto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4dc50-102">How to: Access Members of an Object (Visual Basic)</span></span>

<span data-ttu-id="4dc50-103">Quando si dispone di una variabile oggetto che fa riferimento a un oggetto, spesso si desidera lavorare con i membri di tale oggetto, ad esempio i metodi, le proprietà, i campi e gli eventi.</span><span class="sxs-lookup"><span data-stu-id="4dc50-103">When you have an object variable that refers to an object, you often want to work with the members of that object, such as its methods, properties, fields, and events.</span></span> <span data-ttu-id="4dc50-104">Ad esempio, dopo aver creato un nuovo <xref:System.Windows.Forms.Form> oggetto, potrebbe essere necessario impostare la relativa <xref:System.Windows.Forms.Control.Text%2A> proprietà o chiamarne il <xref:System.Windows.Forms.Control.Focus%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="4dc50-104">For example, once you have created a new <xref:System.Windows.Forms.Form> object, you might want to set its <xref:System.Windows.Forms.Control.Text%2A> property or call its <xref:System.Windows.Forms.Control.Focus%2A> method.</span></span>

## <a name="accessing-members"></a><span data-ttu-id="4dc50-105">Accesso ai membri</span><span class="sxs-lookup"><span data-stu-id="4dc50-105">Accessing Members</span></span>

<span data-ttu-id="4dc50-106">È possibile accedere ai membri di un oggetto tramite la variabile che vi fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="4dc50-106">You access an object's members through the variable that refers to it.</span></span>

#### <a name="to-access-members-of-an-object"></a><span data-ttu-id="4dc50-107">Per accedere ai membri di un oggetto</span><span class="sxs-lookup"><span data-stu-id="4dc50-107">To access members of an object</span></span>

- <span data-ttu-id="4dc50-108">Utilizzare l'operatore di accesso ai membri ( `.` ) tra il nome della variabile oggetto e il nome del membro.</span><span class="sxs-lookup"><span data-stu-id="4dc50-108">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>

    ```vb
    currentText = newForm.Text
    ```

    <span data-ttu-id="4dc50-109">Se il membro è [condiviso](../../../language-reference/modifiers/shared.md), non è necessaria una variabile per accedervi.</span><span class="sxs-lookup"><span data-stu-id="4dc50-109">If the member is [Shared](../../../language-reference/modifiers/shared.md), you do not need a variable to access it.</span></span>

## <a name="accessing-members-of-an-object-of-known-type"></a><span data-ttu-id="4dc50-110">Accesso ai membri di un oggetto di tipo noto</span><span class="sxs-lookup"><span data-stu-id="4dc50-110">Accessing Members of an Object of Known Type</span></span>

<span data-ttu-id="4dc50-111">Se si conosce il tipo di un oggetto in fase di compilazione, è possibile usare l' *associazione anticipata* per una variabile che vi fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="4dc50-111">If you know the type of an object at compile time, you can use *early binding* for a variable that refers to it.</span></span>

#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a><span data-ttu-id="4dc50-112">Per accedere ai membri di un oggetto per il quale si conosce il tipo in fase di compilazione</span><span class="sxs-lookup"><span data-stu-id="4dc50-112">To access members of an object for which you know the type at compile time</span></span>

1. <span data-ttu-id="4dc50-113">Dichiarare la variabile oggetto in modo che sia del tipo dell'oggetto che si intende assegnare alla variabile.</span><span class="sxs-lookup"><span data-stu-id="4dc50-113">Declare the object variable to be of the type of the object you intend to assign to the variable.</span></span>

    ```vb
    Dim extraForm As System.Windows.Forms.Form
    ```

    <span data-ttu-id="4dc50-114">Con `Option Strict On` è possibile assegnare solo <xref:System.Windows.Forms.Form> oggetti (o oggetti di un tipo derivato da <xref:System.Windows.Forms.Form> ) a `extraForm` .</span><span class="sxs-lookup"><span data-stu-id="4dc50-114">With `Option Strict On`, you can assign only <xref:System.Windows.Forms.Form> objects (or objects of a type derived from <xref:System.Windows.Forms.Form>) to `extraForm`.</span></span> <span data-ttu-id="4dc50-115">Se è stata definita una classe o una struttura con una conversione verso un tipo di dati più ampio `CType` <xref:System.Windows.Forms.Form> , è anche possibile assegnare tale classe o struttura a `extraForm` .</span><span class="sxs-lookup"><span data-stu-id="4dc50-115">If you have defined a class or structure with a widening `CType` conversion to <xref:System.Windows.Forms.Form>, you can also assign that class or structure to `extraForm`.</span></span>

2. <span data-ttu-id="4dc50-116">Utilizzare l'operatore di accesso ai membri ( `.` ) tra il nome della variabile oggetto e il nome del membro.</span><span class="sxs-lookup"><span data-stu-id="4dc50-116">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>

    ```vb
    extraForm.Show()
    ```

    <span data-ttu-id="4dc50-117">È possibile accedere a tutti i metodi e le proprietà specifici della <xref:System.Windows.Forms.Form> classe, a prescindere dall' `Option Strict` impostazione.</span><span class="sxs-lookup"><span data-stu-id="4dc50-117">You can access all of the methods and properties specific to the <xref:System.Windows.Forms.Form> class, no matter what the `Option Strict` setting is.</span></span>

## <a name="accessing-members-of-an-object-of-unknown-type"></a><span data-ttu-id="4dc50-118">Accesso ai membri di un oggetto di tipo sconosciuto</span><span class="sxs-lookup"><span data-stu-id="4dc50-118">Accessing Members of an Object of Unknown Type</span></span>

<span data-ttu-id="4dc50-119">Se non si conosce il tipo di un oggetto in fase di compilazione, è necessario usare l' *associazione tardiva* per qualsiasi variabile che vi faccia riferimento.</span><span class="sxs-lookup"><span data-stu-id="4dc50-119">If you do not know the type of an object at compile time, you must use *late binding* for any variable that refers to it.</span></span>

#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a><span data-ttu-id="4dc50-120">Per accedere ai membri di un oggetto per il quale non si conosce il tipo in fase di compilazione</span><span class="sxs-lookup"><span data-stu-id="4dc50-120">To access members of an object for which you do not know the type at compile time</span></span>

1. <span data-ttu-id="4dc50-121">Dichiarare la variabile oggetto in modo che sia del [tipo di dati Object](../../../language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="4dc50-121">Declare the object variable to be of the [Object Data Type](../../../language-reference/data-types/object-data-type.md).</span></span> <span data-ttu-id="4dc50-122">(Dichiarando una variabile come `Object` la dichiarata come <xref:System.Object?displayProperty=nameWithType> ).</span><span class="sxs-lookup"><span data-stu-id="4dc50-122">(Declaring a variable as `Object` is the same as declaring it as <xref:System.Object?displayProperty=nameWithType>.)</span></span>

    ```vb
    Dim someControl As Object
    ```

    <span data-ttu-id="4dc50-123">Con `Option Strict On` , è possibile accedere solo ai membri definiti nella <xref:System.Object> classe.</span><span class="sxs-lookup"><span data-stu-id="4dc50-123">With `Option Strict On`, you can access only the members that are defined on the <xref:System.Object> class.</span></span>

2. <span data-ttu-id="4dc50-124">Utilizzare l'operatore di accesso ai membri ( `.` ) tra il nome della variabile oggetto e il nome del membro.</span><span class="sxs-lookup"><span data-stu-id="4dc50-124">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>

    ```vb
    someControl.GetType()
    ```

    <span data-ttu-id="4dc50-125">Per poter accedere ai membri di qualsiasi oggetto assegnato alla variabile oggetto, è necessario impostare `Option Strict Off` .</span><span class="sxs-lookup"><span data-stu-id="4dc50-125">To be able to access the members of any object you assign to the object variable, you must set `Option Strict Off`.</span></span> <span data-ttu-id="4dc50-126">Quando si esegue questa operazione, il compilatore non può garantire che un determinato membro venga esposto dall'oggetto assegnato alla variabile.</span><span class="sxs-lookup"><span data-stu-id="4dc50-126">When you do this, the compiler cannot guarantee that a given member is exposed by the object you assign to the variable.</span></span> <span data-ttu-id="4dc50-127">Se l'oggetto non espone un membro a cui si tenta di accedere, <xref:System.MemberAccessException> si verificherà un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="4dc50-127">If the object does not expose a member you attempt to access, a <xref:System.MemberAccessException> exception occurs.</span></span>

## <a name="see-also"></a><span data-ttu-id="4dc50-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4dc50-128">See also</span></span>

- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [<span data-ttu-id="4dc50-129">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="4dc50-129">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="4dc50-130">Dichiarazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="4dc50-130">Object Variable Declaration</span></span>](object-variable-declaration.md)
- [<span data-ttu-id="4dc50-131">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="4dc50-131">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="4dc50-132">Option Strict Statement</span><span class="sxs-lookup"><span data-stu-id="4dc50-132">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
