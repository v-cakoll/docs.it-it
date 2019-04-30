---
title: 'Procedura: Accedere ai membri di un oggetto (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: de00e428cc3d9d7a5688e853b0ff4295fec5b3e9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052131"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a><span data-ttu-id="c1c89-102">Procedura: Accedere ai membri di un oggetto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1c89-102">How to: Access Members of an Object (Visual Basic)</span></span>
<span data-ttu-id="c1c89-103">Quando si dispone di una variabile oggetto che fa riferimento a un oggetto, è spesso necessario lavorare con i membri di tale oggetto, ad esempio relativi metodi, proprietà, campi ed eventi.</span><span class="sxs-lookup"><span data-stu-id="c1c89-103">When you have an object variable that refers to an object, you often want to work with the members of that object, such as its methods, properties, fields, and events.</span></span> <span data-ttu-id="c1c89-104">Ad esempio, dopo aver creato un nuovo <xref:System.Windows.Forms.Form> dell'oggetto, si potrebbe voler impostare relativi <xref:System.Windows.Forms.Control.Text%2A> proprietà o chiamata relativo <xref:System.Windows.Forms.Control.Focus%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="c1c89-104">For example, once you have created a new <xref:System.Windows.Forms.Form> object, you might want to set its <xref:System.Windows.Forms.Control.Text%2A> property or call its <xref:System.Windows.Forms.Control.Focus%2A> method.</span></span>  
  
## <a name="accessing-members"></a><span data-ttu-id="c1c89-105">L'accesso ai membri</span><span class="sxs-lookup"><span data-stu-id="c1c89-105">Accessing Members</span></span>  
 <span data-ttu-id="c1c89-106">Membri di un oggetto si accede tramite la variabile che vi fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="c1c89-106">You access an object's members through the variable that refers to it.</span></span>  
  
#### <a name="to-access-members-of-an-object"></a><span data-ttu-id="c1c89-107">Per accedere ai membri di un oggetto</span><span class="sxs-lookup"><span data-stu-id="c1c89-107">To access members of an object</span></span>  
  
- <span data-ttu-id="c1c89-108">Usare l'operatore di accesso ai membri (`.`) tra il nome della variabile oggetto e il nome del membro.</span><span class="sxs-lookup"><span data-stu-id="c1c89-108">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>  
  
    ```  
    currentText = newForm.Text  
    ```  
  
     <span data-ttu-id="c1c89-109">Se il membro [condiviso](../../../../visual-basic/language-reference/modifiers/shared.md), non è necessaria una variabile per accedervi.</span><span class="sxs-lookup"><span data-stu-id="c1c89-109">If the member is [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), you do not need a variable to access it.</span></span>  
  
## <a name="accessing-members-of-an-object-of-known-type"></a><span data-ttu-id="c1c89-110">L'accesso ai membri di un oggetto di tipo conosciuto</span><span class="sxs-lookup"><span data-stu-id="c1c89-110">Accessing Members of an Object of Known Type</span></span>  
 <span data-ttu-id="c1c89-111">Se si conosce il tipo di un oggetto in fase di compilazione, è possibile usare *associazione anticipata* per una variabile che vi fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="c1c89-111">If you know the type of an object at compile time, you can use *early binding* for a variable that refers to it.</span></span>  
  
#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a><span data-ttu-id="c1c89-112">Per accedere ai membri di un oggetto per cui si conosce il tipo in fase di compilazione</span><span class="sxs-lookup"><span data-stu-id="c1c89-112">To access members of an object for which you know the type at compile time</span></span>  
  
1. <span data-ttu-id="c1c89-113">Dichiarare la variabile oggetto di tipo dell'oggetto che si intende assegnare alla variabile.</span><span class="sxs-lookup"><span data-stu-id="c1c89-113">Declare the object variable to be of the type of the object you intend to assign to the variable.</span></span>  
  
    ```  
    Dim extraForm As System.Windows.Forms.Form  
    ```  
  
     <span data-ttu-id="c1c89-114">Con `Option Strict On`, è possibile assegnare solo <xref:System.Windows.Forms.Form> oggetti (o gli oggetti di un tipo derivato da <xref:System.Windows.Forms.Form>) a `extraForm`.</span><span class="sxs-lookup"><span data-stu-id="c1c89-114">With `Option Strict On`, you can assign only <xref:System.Windows.Forms.Form> objects (or objects of a type derived from <xref:System.Windows.Forms.Form>) to `extraForm`.</span></span> <span data-ttu-id="c1c89-115">Se è stato definito una classe o struttura con un ampliamento `CType` conversione <xref:System.Windows.Forms.Form>, è anche possibile assegnare tale classe o struttura a `extraForm`.</span><span class="sxs-lookup"><span data-stu-id="c1c89-115">If you have defined a class or structure with a widening `CType` conversion to <xref:System.Windows.Forms.Form>, you can also assign that class or structure to `extraForm`.</span></span>  
  
2. <span data-ttu-id="c1c89-116">Usare l'operatore di accesso ai membri (`.`) tra il nome della variabile oggetto e il nome del membro.</span><span class="sxs-lookup"><span data-stu-id="c1c89-116">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>  
  
    ```  
    extraForm.Show()  
    ```  
  
     <span data-ttu-id="c1c89-117">È possibile accedere a tutti i metodi e proprietà specifiche per il <xref:System.Windows.Forms.Form> (classe), indipendentemente il `Option Strict` impostazione.</span><span class="sxs-lookup"><span data-stu-id="c1c89-117">You can access all of the methods and properties specific to the <xref:System.Windows.Forms.Form> class, no matter what the `Option Strict` setting is.</span></span>  
  
## <a name="accessing-members-of-an-object-of-unknown-type"></a><span data-ttu-id="c1c89-118">L'accesso ai membri di un oggetto di tipo sconosciuto</span><span class="sxs-lookup"><span data-stu-id="c1c89-118">Accessing Members of an Object of Unknown Type</span></span>  
 <span data-ttu-id="c1c89-119">Se non si conosce il tipo di un oggetto in fase di compilazione, è necessario utilizzare *associazione tardiva* per qualsiasi variabile che vi fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="c1c89-119">If you do not know the type of an object at compile time, you must use *late binding* for any variable that refers to it.</span></span>  
  
#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a><span data-ttu-id="c1c89-120">Per accedere ai membri di un oggetto per cui non si conosce il tipo in fase di compilazione</span><span class="sxs-lookup"><span data-stu-id="c1c89-120">To access members of an object for which you do not know the type at compile time</span></span>  
  
1. <span data-ttu-id="c1c89-121">Dichiarare la variabile di oggetto di [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="c1c89-121">Declare the object variable to be of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span> <span data-ttu-id="c1c89-122">(Dichiarazione di una variabile come `Object` equivale dichiararla come <xref:System.Object?displayProperty=nameWithType>.)</span><span class="sxs-lookup"><span data-stu-id="c1c89-122">(Declaring a variable as `Object` is the same as declaring it as <xref:System.Object?displayProperty=nameWithType>.)</span></span>  
  
    ```  
    Dim someControl As Object  
    ```  
  
     <span data-ttu-id="c1c89-123">Con `Option Strict On`, è possibile accedere solo i membri che sono definiti nel <xref:System.Object> classe.</span><span class="sxs-lookup"><span data-stu-id="c1c89-123">With `Option Strict On`, you can access only the members that are defined on the <xref:System.Object> class.</span></span>  
  
2. <span data-ttu-id="c1c89-124">Usare l'operatore di accesso ai membri (`.`) tra il nome della variabile oggetto e il nome del membro.</span><span class="sxs-lookup"><span data-stu-id="c1c89-124">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>  
  
    ```  
    someControl.GetType()  
    ```  
  
     <span data-ttu-id="c1c89-125">Per poter accedere ai membri di qualsiasi oggetto assegnato alla variabile di oggetto, è necessario impostare `Option Strict Off`.</span><span class="sxs-lookup"><span data-stu-id="c1c89-125">To be able to access the members of any object you assign to the object variable, you must set `Option Strict Off`.</span></span> <span data-ttu-id="c1c89-126">Quando si esegue questa operazione, il compilatore non può garantire che un determinato membro viene esposta dall'oggetto a cui che si assegna alla variabile.</span><span class="sxs-lookup"><span data-stu-id="c1c89-126">When you do this, the compiler cannot guarantee that a given member is exposed by the object you assign to the variable.</span></span> <span data-ttu-id="c1c89-127">Se l'oggetto non espone un membro a cui si tenta di accedere, un <xref:System.MemberAccessException> si verifica un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c1c89-127">If the object does not expose a member you attempt to access, a <xref:System.MemberAccessException> exception occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1c89-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1c89-128">See also</span></span>

- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [<span data-ttu-id="c1c89-129">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="c1c89-129">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="c1c89-130">Dichiarazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="c1c89-130">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="c1c89-131">Tipo di dati Object</span><span class="sxs-lookup"><span data-stu-id="c1c89-131">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="c1c89-132">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="c1c89-132">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
