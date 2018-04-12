---
title: Istruzione Enum (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Enum
helpviewer_keywords:
- enumerated constants [Visual Basic]
- Enum statement [Visual Basic]
- Private keyword [Visual Basic], Enum statements
- Public keyword [Visual Basic], in Enum statement
- variables [Visual Basic], enumeration
- constants [Visual Basic], enumerated
ms.assetid: a45e51f1-65ff-48e1-bf32-79130f137377
caps.latest.revision: 44
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7a8244318e0be8e50f3384b56cf63e59182b6cda
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="enum-statement-visual-basic"></a><span data-ttu-id="9b8f0-102">Istruzione Enum (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b8f0-102">Enum Statement (Visual Basic)</span></span>
<span data-ttu-id="9b8f0-103">Dichiara un'enumerazione e definisce i valori dei relativi membri.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-103">Declares an enumeration and defines the values of its members.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b8f0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9b8f0-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]   
Enum enumerationname [ As datatype ]   
   memberlist  
End Enum  
```  
  
## <a name="parts"></a><span data-ttu-id="9b8f0-105">Parti</span><span class="sxs-lookup"><span data-stu-id="9b8f0-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="9b8f0-106">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-106">Optional.</span></span> <span data-ttu-id="9b8f0-107">Elenco di attributi che si applicano a questa enumerazione.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-107">List of attributes that apply to this enumeration.</span></span> <span data-ttu-id="9b8f0-108">È necessario racchiudere il [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md) tra parentesi quadre ("`<`"e"`>`").</span><span class="sxs-lookup"><span data-stu-id="9b8f0-108">You must enclose the [attribute list](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
     <span data-ttu-id="9b8f0-109">Il <xref:System.FlagsAttribute> attributo indica che il valore di un'istanza dell'enumerazione può includere più membri di enumerazione e che ogni membro rappresenta un campo di bit nel valore di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-109">The <xref:System.FlagsAttribute> attribute indicates that the value of an instance of the enumeration can include multiple enumeration members, and that each member represents a bit field in the enumeration value.</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="9b8f0-110">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-110">Optional.</span></span> <span data-ttu-id="9b8f0-111">Specifica il codice può accedere a questa enumerazione.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-111">Specifies what code can access this enumeration.</span></span> <span data-ttu-id="9b8f0-112">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b8f0-112">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="9b8f0-113">Public</span><span class="sxs-lookup"><span data-stu-id="9b8f0-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="9b8f0-114">Protected</span><span class="sxs-lookup"><span data-stu-id="9b8f0-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="9b8f0-115">Friend</span><span class="sxs-lookup"><span data-stu-id="9b8f0-115">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="9b8f0-116">Private</span><span class="sxs-lookup"><span data-stu-id="9b8f0-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
     <span data-ttu-id="9b8f0-117">È possibile specificare `Protected``Friend` per consentire l'accesso dal codice all'interno dello stesso assembly, una classe derivata o nella classe dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-117">You can specify `Protected``Friend` to allow access from code within the enumeration's class, a derived class, or the same assembly.</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="9b8f0-118">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-118">Optional.</span></span> <span data-ttu-id="9b8f0-119">Specifica che questa enumerazione ridichiara e nasconde un elemento di programmazione omonimo o un set di elementi in overload di una classe di base.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-119">Specifies that this enumeration redeclares and hides an identically named programming element, or set of overloaded elements, in a base class.</span></span> <span data-ttu-id="9b8f0-120">È possibile specificare [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) solo sull'enumerazione, non sui relativi membri.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-120">You can specify [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) only on the enumeration itself, not on any of its members.</span></span>  
  
-   `enumerationname`  
  
     <span data-ttu-id="9b8f0-121">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-121">Required.</span></span> <span data-ttu-id="9b8f0-122">Nome dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-122">Name of the enumeration.</span></span> <span data-ttu-id="9b8f0-123">Per informazioni sui nomi validi, vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="9b8f0-123">For information on valid names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `datatype`  
  
     <span data-ttu-id="9b8f0-124">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-124">Optional.</span></span> <span data-ttu-id="9b8f0-125">Tipo di dati di enumerazione e tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-125">Data type of the enumeration and all its members.</span></span>  
  
-   `memberlist`  
  
     <span data-ttu-id="9b8f0-126">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-126">Required.</span></span> <span data-ttu-id="9b8f0-127">Elenco di costanti di membro dichiarate in questa istruzione.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-127">List of member constants being declared in this statement.</span></span> <span data-ttu-id="9b8f0-128">Più membri vengono visualizzati in righe di codice sorgente singoli.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-128">Multiple members appear on individual source code lines.</span></span>  
  
     <span data-ttu-id="9b8f0-129">Ogni `member` ha la sintassi e le parti seguenti:`[<attribute list>] member name [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="9b8f0-129">Each `member` has the following syntax and parts: `[<attribute list>] member name [ = initializer ]`</span></span>  
  
    |<span data-ttu-id="9b8f0-130">Parte</span><span class="sxs-lookup"><span data-stu-id="9b8f0-130">Part</span></span>|<span data-ttu-id="9b8f0-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9b8f0-131">Description</span></span>|  
    |---|---|  
    |`membername`|<span data-ttu-id="9b8f0-132">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-132">Required.</span></span> <span data-ttu-id="9b8f0-133">Nome del membro.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-133">Name of this member.</span></span>|  
    |`initializer`|<span data-ttu-id="9b8f0-134">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-134">Optional.</span></span> <span data-ttu-id="9b8f0-135">Espressione che viene valutata in fase di compilazione e assegnata al membro.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-135">Expression that is evaluated at compile time and assigned to this member.</span></span>|  
  
-   <span data-ttu-id="9b8f0-136">`End` `Enum`</span><span class="sxs-lookup"><span data-stu-id="9b8f0-136">`End` `Enum`</span></span>  
  
     <span data-ttu-id="9b8f0-137">Termina il blocco `Enum`.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-137">Terminates the `Enum` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b8f0-138">Note</span><span class="sxs-lookup"><span data-stu-id="9b8f0-138">Remarks</span></span>  
 <span data-ttu-id="9b8f0-139">Se si dispone di un set di valori fissi logicamente correlati tra loro, è possibile definirli insieme in un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-139">If you have a set of unchanging values that are logically related to each other, you can define them together in an enumeration.</span></span> <span data-ttu-id="9b8f0-140">In questo modo i nomi significativi per l'enumerazione e i relativi membri, che sono più facili da ricordare rispetto ai relativi valori.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-140">This provides meaningful names for the enumeration and its members, which are easier to remember than their values.</span></span> <span data-ttu-id="9b8f0-141">È quindi possibile utilizzare i membri di enumerazione in numerose posizioni nel codice.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-141">You can then use the enumeration members in many places in your code.</span></span>  
  
 <span data-ttu-id="9b8f0-142">Di seguito sono indicati i vantaggi dell'utilizzo di enumerazioni:</span><span class="sxs-lookup"><span data-stu-id="9b8f0-142">The benefits of using enumerations include the following:</span></span>  
  
-   <span data-ttu-id="9b8f0-143">Per ridurre gli errori causati dalla trasposizione o numeri di errori di digitazione.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-143">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
-   <span data-ttu-id="9b8f0-144">Consente di modificare i valori in futuro.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-144">Makes it easy to change values in the future.</span></span>  
  
-   <span data-ttu-id="9b8f0-145">Rende il codice più facile da leggere, pertanto che è meno probabile che gli errori verranno introdotte.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-145">Makes code easier to read, which means it is less likely that errors will be introduced.</span></span>  
  
-   <span data-ttu-id="9b8f0-146">Garantisce la compatibilità.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-146">Ensures forward compatibility.</span></span> <span data-ttu-id="9b8f0-147">Se si utilizzano le enumerazioni, il codice è meno probabile che se in futuro un utente modifica i valori corrispondenti ai nomi dei membri.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-147">If you use enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
 <span data-ttu-id="9b8f0-148">Un'enumerazione ha un nome, tipo di dati sottostante e un set di membri.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-148">An enumeration has a name, an underlying data type, and a set of members.</span></span> <span data-ttu-id="9b8f0-149">Ogni membro rappresenta una costante.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-149">Each member represents a constant.</span></span>  
  
 <span data-ttu-id="9b8f0-150">È un'enumerazione dichiarata nella classe, struttura, modulo o il livello di interfaccia, all'esterno di qualsiasi routine, un *enumerazione membro*.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-150">An enumeration declared at class, structure, module, or interface level, outside any procedure, is a *member enumeration*.</span></span> <span data-ttu-id="9b8f0-151">È un membro della classe, struttura, modulo o interfaccia che lo dichiara.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-151">It is a member of the class, structure, module, or interface that declares it.</span></span>  
  
 <span data-ttu-id="9b8f0-152">Enumerazioni di membro essere accessibili da qualsiasi punto all'interno di loro classe, struttura, modulo o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-152">Member enumerations can be accessed from anywhere within their class, structure, module, or interface.</span></span> <span data-ttu-id="9b8f0-153">Codice esterno di una classe, struttura o un modulo necessario qualificare il nome di un'enumerazione di membri con il nome di tale classe, struttura o modulo.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-153">Code outside a class, structure, or module must qualify a member enumeration's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="9b8f0-154">È possibile evitare la necessità di utilizzare nomi completi aggiungendo un [importazioni](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) istruzione per il file di origine.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-154">You can avoid the need to use fully qualified names by adding an [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statement to the source file.</span></span>  
  
 <span data-ttu-id="9b8f0-155">Un'enumerazione dichiarata a livello di spazio dei nomi, all'esterno di qualsiasi classe, struttura, modulo o interfaccia, è un membro dello spazio dei nomi in cui è presente.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-155">An enumeration declared at namespace level, outside any class, structure, module, or interface, is a member of the namespace in which it appears.</span></span>  
  
 <span data-ttu-id="9b8f0-156">Il *contesto della dichiarazione* per un'enumerazione deve essere un file di origine, lo spazio dei nomi, classe, struttura, modulo o interfaccia e non può essere una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-156">The *declaration context* for an enumeration must be a source file, namespace, class, structure, module, or interface, and cannot be a procedure.</span></span> <span data-ttu-id="9b8f0-157">Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="9b8f0-157">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="9b8f0-158">È possibile applicare attributi a un'enumerazione nel suo complesso, ma non ai relativi membri singolarmente.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-158">You can apply attributes to an enumeration as a whole, but not to its members individually.</span></span> <span data-ttu-id="9b8f0-159">Un attributo fornisce informazioni per i metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-159">An attribute contributes information to the assembly's metadata.</span></span>  
  
## <a name="data-type"></a><span data-ttu-id="9b8f0-160">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9b8f0-160">Data Type</span></span>  
 <span data-ttu-id="9b8f0-161">Il `Enum` istruzione può dichiarare il tipo di dati di un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-161">The `Enum` statement can declare the data type of an enumeration.</span></span> <span data-ttu-id="9b8f0-162">Ciascun membro viene attribuito il tipo di dati dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-162">Each member takes the enumeration's data type.</span></span> <span data-ttu-id="9b8f0-163">È possibile specificare `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, o `UShort`.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-163">You can specify `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort`.</span></span>  
  
 <span data-ttu-id="9b8f0-164">Se non si specifica `datatype` per l'enumerazione, ogni membro accetta il tipo di dati relativo `initializer`.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-164">If you do not specify `datatype` for the enumeration, each member takes the data type of its `initializer`.</span></span> <span data-ttu-id="9b8f0-165">Se si specificano entrambi `datatype` e `initializer`, il tipo di dati `initializer` deve essere convertibile in `datatype`.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-165">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="9b8f0-166">Se non si specifica `datatype` né `initializer` è presente, il tipo di dati predefinite per `Integer`.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-166">If neither `datatype` nor `initializer` is present, the data type defaults to `Integer`.</span></span>  
  
## <a name="initializing-members"></a><span data-ttu-id="9b8f0-167">L'inizializzazione dei membri</span><span class="sxs-lookup"><span data-stu-id="9b8f0-167">Initializing Members</span></span>  
 <span data-ttu-id="9b8f0-168">Il `Enum` istruzione è possibile inizializzare il contenuto di membri selezionati in `memberlist`.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-168">The `Enum` statement can initialize the contents of selected members in `memberlist`.</span></span> <span data-ttu-id="9b8f0-169">Utilizzare `initializer` per fornire un'espressione da assegnare al membro.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-169">You use `initializer` to supply an expression to be assigned to the member.</span></span>  
  
 <span data-ttu-id="9b8f0-170">Se non si specifica `initializer` per un membro, Visual Basic inizializzato su zero (se è il primo `member` in `memberlist`), o su un valore maggiore di uno rispetto a quello dell'oggetto immediatamente precedente `member`.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-170">If you do not specify `initializer` for a member, Visual Basic initializes it either to zero (if it is the first `member` in `memberlist`), or to a value greater by one than that of the immediately preceding `member`.</span></span>  
  
 <span data-ttu-id="9b8f0-171">L'espressione fornita in ciascun `initializer` può essere qualsiasi combinazione di valori letterali, sono già definite altre costanti e membri di enumerazione che sono già definiti, incluso un membro precedente di questa enumerazione.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-171">The expression supplied in each `initializer` can be any combination of literals, other constants that are already defined, and enumeration members that are already defined, including a previous member of this enumeration.</span></span> <span data-ttu-id="9b8f0-172">È possibile utilizzare gli operatori aritmetici e logici per combinare tali elementi.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-172">You can use arithmetic and logical operators to combine such elements.</span></span>  
  
 <span data-ttu-id="9b8f0-173">Non è possibile utilizzare variabili o funzioni `initializer`.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-173">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="9b8f0-174">Tuttavia, è possibile utilizzare parole chiave di conversione, ad esempio `CByte` e `CShort`.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-174">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="9b8f0-175">È inoltre possibile utilizzare `AscW` se viene chiamata con una costante `String` o `Char` argomento, dal momento che può essere valutato in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-175">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>  
  
 <span data-ttu-id="9b8f0-176">Enumerazioni non possono avere valori a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-176">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="9b8f0-177">Se un membro viene assegnato un valore a virgola mobile e `Option Strict` è impostata su on, si verifica un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-177">If a member is assigned a floating-point value and `Option Strict` is set to on, a compiler error occurs.</span></span> <span data-ttu-id="9b8f0-178">Se `Option Strict` è disattivata, il valore viene convertito automaticamente nel `Enum` tipo.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-178">If `Option Strict` is off, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="9b8f0-179">Se il valore di un membro supera l'intervallo consentito per il tipo di dati sottostante o se si inizializza un membro del valore massimo consentito dal tipo di dati sottostante, il compilatore segnala un errore.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-179">If the value of a member exceeds the allowable range for the underlying data type, or if you initialize any member to the maximum value allowed by the underlying data type, the compiler reports an error.</span></span>  
  
## <a name="modifiers"></a><span data-ttu-id="9b8f0-180">Modificatori</span><span class="sxs-lookup"><span data-stu-id="9b8f0-180">Modifiers</span></span>  
 <span data-ttu-id="9b8f0-181">Classe, struttura, modulo e predefinito enumerazioni membro di interfaccia di accesso pubblico.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-181">Class, structure, module, and interface member enumerations default to public access.</span></span> <span data-ttu-id="9b8f0-182">È possibile regolare i livelli di accesso con i modificatori di accesso.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-182">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="9b8f0-183">Namespace membro enumerazioni per impostazione predefinita l'accesso friend.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-183">Namespace member enumerations default to friend access.</span></span> <span data-ttu-id="9b8f0-184">È possibile regolare i livelli di accesso al ruolo public, ma non a privato o protetto.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-184">You can adjust their access levels to public, but not to private or protected.</span></span> <span data-ttu-id="9b8f0-185">Per ulteriori informazioni, vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="9b8f0-185">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="9b8f0-186">Tutti i membri di enumerazione dispongono di accesso pubblico e non è possibile utilizzare i modificatori di accesso su di essi.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-186">All enumeration members have public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="9b8f0-187">Tuttavia, se l'enumerazione dispone di un livello di accesso più limitato, il livello di accesso di enumerazione specificato ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-187">However, if the enumeration itself has a more restricted access level, the specified enumeration access level takes precedence.</span></span>  
  
 <span data-ttu-id="9b8f0-188">Per impostazione predefinita, tutte le enumerazioni sono tipi e i relativi campi sono costanti.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-188">By default, all enumerations are types and their fields are constants.</span></span> <span data-ttu-id="9b8f0-189">Pertanto il `Shared`, `Static`, e `ReadOnly` parole chiave non possono essere utilizzate quando si dichiara un'enumerazione o i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-189">Therefore the `Shared`, `Static`, and `ReadOnly` keywords cannot be used when declaring an enumeration or its members.</span></span>  
  
## <a name="assigning-multiple-values"></a><span data-ttu-id="9b8f0-190">L'assegnazione di più valori</span><span class="sxs-lookup"><span data-stu-id="9b8f0-190">Assigning Multiple Values</span></span>  
 <span data-ttu-id="9b8f0-191">In genere, le enumerazioni rappresentano valori si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-191">Enumerations typically represent mutually exclusive values.</span></span> <span data-ttu-id="9b8f0-192">Includendo la <xref:System.FlagsAttribute> attributo la `Enum` dichiarazione, è possibile invece assegnare più valori a un'istanza dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-192">By including the <xref:System.FlagsAttribute> attribute in the `Enum` declaration, you can instead assign multiple values to an instance of the enumeration.</span></span> <span data-ttu-id="9b8f0-193">Il <xref:System.FlagsAttribute> attributo specifica che l'enumerazione deve essere considerata come un campo di bit, ovvero un set di flag.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-193">The <xref:System.FlagsAttribute> attribute specifies that the enumeration be treated as a bit field, that is, a set of flags.</span></span> <span data-ttu-id="9b8f0-194">Questi sono denominati *bit per bit* enumerazioni.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-194">These are called *bitwise* enumerations.</span></span>  
  
 <span data-ttu-id="9b8f0-195">Quando si dichiara un'enumerazione tramite il <xref:System.FlagsAttribute> attributo, è consigliabile utilizzare potenze di 2, ovvero, 1, 2, 4, 8, 16 e così via, per i valori.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-195">When you declare an enumeration by using the <xref:System.FlagsAttribute> attribute, we recommend that you use powers of 2, that is, 1, 2, 4, 8, 16, and so on, for the values.</span></span> <span data-ttu-id="9b8f0-196">È inoltre consigliabile "None" il nome di un membro il cui valore è 0.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-196">We also recommend that "None" be the name of a member whose value is 0.</span></span> <span data-ttu-id="9b8f0-197">Per ulteriori istruzioni, vedere <xref:System.FlagsAttribute> e <xref:System.Enum>.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-197">For additional guidelines, see <xref:System.FlagsAttribute> and <xref:System.Enum>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b8f0-198">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b8f0-198">Example</span></span>  
 <span data-ttu-id="9b8f0-199">Nell'esempio seguente viene illustrato come utilizzare il `Enum` istruzione.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-199">The following example shows how to use the `Enum` statement.</span></span> <span data-ttu-id="9b8f0-200">Si noti che il membro è detto `EggSizeEnum.Medium`e non come `Medium`.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-200">Note that the member is referred to as `EggSizeEnum.Medium`, and not as `Medium`.</span></span>  
  
 [!code-vb[VbEnumsTask#41](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="9b8f0-201">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b8f0-201">Example</span></span>  
 <span data-ttu-id="9b8f0-202">Nell'esempio seguente il metodo non è compreso il `Egg` classe.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-202">The method in the following example is outside the `Egg` class.</span></span> <span data-ttu-id="9b8f0-203">Pertanto, `EggSizeEnum` nome completo come `Egg.EggSizeEnum`.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-203">Therefore, `EggSizeEnum` is fully qualified as `Egg.EggSizeEnum`.</span></span>  
  
 [!code-vb[VbEnumsTask#42](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="9b8f0-204">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b8f0-204">Example</span></span>  
 <span data-ttu-id="9b8f0-205">L'esempio seguente usa il `Enum` denominato di istruzione per definire un set correlato di valori costanti.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-205">The following example uses the `Enum` statement to define a related set of named constant values.</span></span> <span data-ttu-id="9b8f0-206">In questo caso, i valori sono i colori che è possibile scegliere di progettare il form di immissione di dati per un database.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-206">In this case, the values are colors you might choose to design data entry forms for a database.</span></span>  
  
 [!code-vb[VbEnumsTask#30](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="9b8f0-207">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b8f0-207">Example</span></span>  
 <span data-ttu-id="9b8f0-208">L'esempio seguente mostra i valori che includono numeri positivi e negativi.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-208">The following example shows values that include both positive and negative numbers.</span></span>  
  
 [!code-vb[VbEnumsTask#31](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_4.vb)]  
  
## <a name="example"></a><span data-ttu-id="9b8f0-209">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b8f0-209">Example</span></span>  
 <span data-ttu-id="9b8f0-210">Nell'esempio seguente, un `As` clausola viene utilizzata per specificare il `datatype` di un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-210">In the following example, an `As` clause is used to specify the `datatype` of an enumeration.</span></span>  
  
 [!code-vb[VbEnumsTask#6](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_5.vb)]  
  
## <a name="example"></a><span data-ttu-id="9b8f0-211">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b8f0-211">Example</span></span>  
 <span data-ttu-id="9b8f0-212">Nell'esempio seguente viene illustrato come utilizzare un'enumerazione bit per bit.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-212">The following example shows how to use a bitwise enumeration.</span></span> <span data-ttu-id="9b8f0-213">Più valori possono essere assegnati a un'istanza di un'enumerazione bit per bit.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-213">Multiple values can be assigned to an instance of a bitwise enumeration.</span></span> <span data-ttu-id="9b8f0-214">Il `Enum` dichiarazione include il <xref:System.FlagsAttribute> attributo, che indica che l'enumerazione può essere gestita come un set di flag.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-214">The `Enum` declaration includes the <xref:System.FlagsAttribute> attribute, which indicates that the enumeration can be treated as a set of flags.</span></span>  
  
 [!code-vb[VbEnumsTask#61](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_6.vb)]  
  
## <a name="example"></a><span data-ttu-id="9b8f0-215">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b8f0-215">Example</span></span>  
 <span data-ttu-id="9b8f0-216">Nell'esempio seguente viene eseguito lo scorrimento a un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-216">The following example iterates through an enumeration.</span></span> <span data-ttu-id="9b8f0-217">Usa il <xref:System.Enum.GetNames%2A> metodo per recuperare una matrice di nomi dei membri dell'enumerazione, e <xref:System.Enum.GetValues%2A> per recuperare una matrice dei valori dei membri.</span><span class="sxs-lookup"><span data-stu-id="9b8f0-217">It uses the <xref:System.Enum.GetNames%2A> method to retrieve an array of member names from the enumeration, and <xref:System.Enum.GetValues%2A> to retrieve an array of member values.</span></span>  
  
 [!code-vb[VbEnumsTask#51](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_7.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="9b8f0-218">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b8f0-218">See Also</span></span>  
 <xref:System.Enum>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 [<span data-ttu-id="9b8f0-219">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="9b8f0-219">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
 [<span data-ttu-id="9b8f0-220">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="9b8f0-220">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="9b8f0-221">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="9b8f0-221">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="9b8f0-222">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="9b8f0-222">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="9b8f0-223">Costanti ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="9b8f0-223">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)
