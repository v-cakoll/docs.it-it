---
title: 'Procedura: accedere ai membri di un oggetto (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 85fa4932b449bf7b9ecb3902fc17fd954ea8cfac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a><span data-ttu-id="f6f64-102">Procedura: accedere ai membri di un oggetto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6f64-102">How to: Access Members of an Object (Visual Basic)</span></span>
<span data-ttu-id="f6f64-103">Quando si dispone di una variabile oggetto che fa riferimento a un oggetto, spesso si desidera lavorare con i membri di tale oggetto, ad esempio i relativi metodi, proprietà, campi ed eventi.</span><span class="sxs-lookup"><span data-stu-id="f6f64-103">When you have an object variable that refers to an object, you often want to work with the members of that object, such as its methods, properties, fields, and events.</span></span> <span data-ttu-id="f6f64-104">Ad esempio, dopo aver creato un nuovo <xref:System.Windows.Forms.Form> dell'oggetto, è possibile impostare il relativo <xref:System.Windows.Forms.Control.Text%2A> chiamata o proprietà relativo <xref:System.Windows.Forms.Control.Focus%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="f6f64-104">For example, once you have created a new <xref:System.Windows.Forms.Form> object, you might want to set its <xref:System.Windows.Forms.Control.Text%2A> property or call its <xref:System.Windows.Forms.Control.Focus%2A> method.</span></span>  
  
## <a name="accessing-members"></a><span data-ttu-id="f6f64-105">L'accesso ai membri</span><span class="sxs-lookup"><span data-stu-id="f6f64-105">Accessing Members</span></span>  
 <span data-ttu-id="f6f64-106">Membri di un oggetto sono accessibili tramite la variabile che fa riferimento a esso.</span><span class="sxs-lookup"><span data-stu-id="f6f64-106">You access an object's members through the variable that refers to it.</span></span>  
  
#### <a name="to-access-members-of-an-object"></a><span data-ttu-id="f6f64-107">Per accedere ai membri di un oggetto</span><span class="sxs-lookup"><span data-stu-id="f6f64-107">To access members of an object</span></span>  
  
-   <span data-ttu-id="f6f64-108">Usare l'operatore di accesso ai membri (`.`) tra il nome della variabile oggetto e il nome del membro.</span><span class="sxs-lookup"><span data-stu-id="f6f64-108">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>  
  
    ```  
    currentText = newForm.Text  
    ```  
  
     <span data-ttu-id="f6f64-109">Se il membro è [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), non è necessaria una variabile per accedervi.</span><span class="sxs-lookup"><span data-stu-id="f6f64-109">If the member is [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), you do not need a variable to access it.</span></span>  
  
## <a name="accessing-members-of-an-object-of-known-type"></a><span data-ttu-id="f6f64-110">L'accesso ai membri di un oggetto di tipo noto</span><span class="sxs-lookup"><span data-stu-id="f6f64-110">Accessing Members of an Object of Known Type</span></span>  
 <span data-ttu-id="f6f64-111">Se si conosce il tipo di un oggetto in fase di compilazione, è possibile utilizzare *associazione anticipata* per una variabile che fa riferimento a esso.</span><span class="sxs-lookup"><span data-stu-id="f6f64-111">If you know the type of an object at compile time, you can use *early binding* for a variable that refers to it.</span></span>  
  
#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a><span data-ttu-id="f6f64-112">Per accedere ai membri di un oggetto per cui si conosce il tipo in fase di compilazione</span><span class="sxs-lookup"><span data-stu-id="f6f64-112">To access members of an object for which you know the type at compile time</span></span>  
  
1.  <span data-ttu-id="f6f64-113">Dichiarare la variabile di oggetto di tipo dell'oggetto a cui che si desidera assegnare alla variabile.</span><span class="sxs-lookup"><span data-stu-id="f6f64-113">Declare the object variable to be of the type of the object you intend to assign to the variable.</span></span>  
  
    ```  
    Dim extraForm As System.Windows.Forms.Form  
    ```  
  
     <span data-ttu-id="f6f64-114">Con `Option Strict On`, è possibile assegnare solo <xref:System.Windows.Forms.Form> oggetti (o gli oggetti di un tipo derivato da <xref:System.Windows.Forms.Form>) a `extraForm`.</span><span class="sxs-lookup"><span data-stu-id="f6f64-114">With `Option Strict On`, you can assign only <xref:System.Windows.Forms.Form> objects (or objects of a type derived from <xref:System.Windows.Forms.Form>) to `extraForm`.</span></span> <span data-ttu-id="f6f64-115">Se si è definite una classe o struttura con un ampliamento `CType` conversione <xref:System.Windows.Forms.Form>, è inoltre possibile assegnare la classe o struttura in `extraForm`.</span><span class="sxs-lookup"><span data-stu-id="f6f64-115">If you have defined a class or structure with a widening `CType` conversion to <xref:System.Windows.Forms.Form>, you can also assign that class or structure to `extraForm`.</span></span>  
  
2.  <span data-ttu-id="f6f64-116">Usare l'operatore di accesso ai membri (`.`) tra il nome della variabile oggetto e il nome del membro.</span><span class="sxs-lookup"><span data-stu-id="f6f64-116">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>  
  
    ```  
    extraForm.Show()  
    ```  
  
     <span data-ttu-id="f6f64-117">È possibile accedere a tutti i metodi e proprietà specifiche per la <xref:System.Windows.Forms.Form> (classe), indipendentemente il `Option Strict` impostazione.</span><span class="sxs-lookup"><span data-stu-id="f6f64-117">You can access all of the methods and properties specific to the <xref:System.Windows.Forms.Form> class, no matter what the `Option Strict` setting is.</span></span>  
  
## <a name="accessing-members-of-an-object-of-unknown-type"></a><span data-ttu-id="f6f64-118">L'accesso ai membri di un oggetto di tipo sconosciuto</span><span class="sxs-lookup"><span data-stu-id="f6f64-118">Accessing Members of an Object of Unknown Type</span></span>  
 <span data-ttu-id="f6f64-119">Se non si conosce il tipo di un oggetto in fase di compilazione, è necessario utilizzare *ad associazione tardiva* per qualsiasi variabile che fa riferimento a esso.</span><span class="sxs-lookup"><span data-stu-id="f6f64-119">If you do not know the type of an object at compile time, you must use *late binding* for any variable that refers to it.</span></span>  
  
#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a><span data-ttu-id="f6f64-120">Per accedere ai membri di un oggetto per cui non si conosce il tipo in fase di compilazione</span><span class="sxs-lookup"><span data-stu-id="f6f64-120">To access members of an object for which you do not know the type at compile time</span></span>  
  
1.  <span data-ttu-id="f6f64-121">Dichiarare la variabile di oggetto di [tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="f6f64-121">Declare the object variable to be of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span> <span data-ttu-id="f6f64-122">(La dichiarazione di una variabile come `Object` corrisponde alla dichiarazione come <xref:System.Object?displayProperty=nameWithType>.)</span><span class="sxs-lookup"><span data-stu-id="f6f64-122">(Declaring a variable as `Object` is the same as declaring it as <xref:System.Object?displayProperty=nameWithType>.)</span></span>  
  
    ```  
    Dim someControl As Object  
    ```  
  
     <span data-ttu-id="f6f64-123">Con `Option Strict On`, è possibile accedere solo i membri che sono definiti nella <xref:System.Object> classe.</span><span class="sxs-lookup"><span data-stu-id="f6f64-123">With `Option Strict On`, you can access only the members that are defined on the <xref:System.Object> class.</span></span>  
  
2.  <span data-ttu-id="f6f64-124">Usare l'operatore di accesso ai membri (`.`) tra il nome della variabile oggetto e il nome del membro.</span><span class="sxs-lookup"><span data-stu-id="f6f64-124">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>  
  
    ```  
    someControl.GetType()  
    ```  
  
     <span data-ttu-id="f6f64-125">Per essere in grado di accedere ai membri di qualsiasi oggetto assegnato alla variabile oggetto, è necessario impostare `Option Strict Off`.</span><span class="sxs-lookup"><span data-stu-id="f6f64-125">To be able to access the members of any object you assign to the object variable, you must set `Option Strict Off`.</span></span> <span data-ttu-id="f6f64-126">Quando si esegue questa operazione, il compilatore non garantisce che un determinato membro viene esposto da oggetto assegnato alla variabile.</span><span class="sxs-lookup"><span data-stu-id="f6f64-126">When you do this, the compiler cannot guarantee that a given member is exposed by the object you assign to the variable.</span></span> <span data-ttu-id="f6f64-127">Se l'oggetto non espone un membro a cui si tenta di accedere, un <xref:System.MemberAccessException> si verifica un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="f6f64-127">If the object does not expose a member you attempt to access, a <xref:System.MemberAccessException> exception occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6f64-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6f64-128">See Also</span></span>  
 <xref:System.Object>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.MemberAccessException>  
 [<span data-ttu-id="f6f64-129">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="f6f64-129">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="f6f64-130">Dichiarazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="f6f64-130">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [<span data-ttu-id="f6f64-131">Tipo di dati Object</span><span class="sxs-lookup"><span data-stu-id="f6f64-131">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="f6f64-132">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="f6f64-132">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
