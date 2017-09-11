---
title: Istruzione Enum (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Enum
dev_langs:
- VB
helpviewer_keywords:
- enumerated constants
- Enum statement
- Private keyword, Enum statements
- Public keyword, in Enum statement
- variables [Visual Basic], enumeration
- constants, enumerated
ms.assetid: a45e51f1-65ff-48e1-bf32-79130f137377
caps.latest.revision: 44
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ff075349756bd4c568833d049b50b3c3721d1b08
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="enum-statement-visual-basic"></a><span data-ttu-id="799f4-102">Istruzione Enum (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="799f4-102">Enum Statement (Visual Basic)</span></span>
<span data-ttu-id="799f4-103">Dichiara un'enumerazione e definisce i valori dei relativi membri.</span><span class="sxs-lookup"><span data-stu-id="799f4-103">Declares an enumeration and defines the values of its members.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="799f4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="799f4-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]   
Enum enumerationname [ As datatype ]   
   memberlist  
End Enum  
```  
  
## <a name="parts"></a><span data-ttu-id="799f4-105">Parti</span><span class="sxs-lookup"><span data-stu-id="799f4-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="799f4-106">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="799f4-106">Optional.</span></span> <span data-ttu-id="799f4-107">Elenco di attributi che si applicano a questa enumerazione.</span><span class="sxs-lookup"><span data-stu-id="799f4-107">List of attributes that apply to this enumeration.</span></span> <span data-ttu-id="799f4-108">È necessario racchiudere il [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md) parentesi angolari ("`<`"e"`>`").</span><span class="sxs-lookup"><span data-stu-id="799f4-108">You must enclose the [attribute list](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
     <span data-ttu-id="799f4-109">Il <xref:System.FlagsAttribute>attributo indica che il valore di un'istanza di enumerazione può includere più membri di enumerazione, e che ogni membro rappresenta un campo di bit nel valore di enumerazione.</xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="799f4-109">The <xref:System.FlagsAttribute> attribute indicates that the value of an instance of the enumeration can include multiple enumeration members, and that each member represents a bit field in the enumeration value.</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="799f4-110">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="799f4-110">Optional.</span></span> <span data-ttu-id="799f4-111">Specifica il codice può accedere a questa enumerazione.</span><span class="sxs-lookup"><span data-stu-id="799f4-111">Specifies what code can access this enumeration.</span></span> <span data-ttu-id="799f4-112">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="799f4-112">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="799f4-113">Public</span><span class="sxs-lookup"><span data-stu-id="799f4-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="799f4-114">Protected</span><span class="sxs-lookup"><span data-stu-id="799f4-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="799f4-115">Friend</span><span class="sxs-lookup"><span data-stu-id="799f4-115">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="799f4-116">Private</span><span class="sxs-lookup"><span data-stu-id="799f4-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
     <span data-ttu-id="799f4-117">È possibile specificare `Protected``Friend` per consentire l'accesso dal codice all'interno dello stesso assembly, una classe derivata o classe dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="799f4-117">You can specify `Protected``Friend` to allow access from code within the enumeration's class, a derived class, or the same assembly.</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="799f4-118">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="799f4-118">Optional.</span></span> <span data-ttu-id="799f4-119">Specifica che l'enumerazione ridichiara e nasconde un elemento di programmazione omonimo o un set di elementi in overload, una classe di base.</span><span class="sxs-lookup"><span data-stu-id="799f4-119">Specifies that this enumeration redeclares and hides an identically named programming element, or set of overloaded elements, in a base class.</span></span> <span data-ttu-id="799f4-120">È possibile specificare [ombreggiature](../../../visual-basic/language-reference/modifiers/shadows.md) solo sull'enumerazione, non sui relativi membri.</span><span class="sxs-lookup"><span data-stu-id="799f4-120">You can specify [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) only on the enumeration itself, not on any of its members.</span></span>  
  
-   `enumerationname`  
  
     <span data-ttu-id="799f4-121">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="799f4-121">Required.</span></span> <span data-ttu-id="799f4-122">Nome dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="799f4-122">Name of the enumeration.</span></span> <span data-ttu-id="799f4-123">Per informazioni sui nomi validi, vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="799f4-123">For information on valid names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `datatype`  
  
     <span data-ttu-id="799f4-124">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="799f4-124">Optional.</span></span> <span data-ttu-id="799f4-125">Tipo di dati dell'enumerazione e tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="799f4-125">Data type of the enumeration and all its members.</span></span>  
  
-   `memberlist`  
  
     <span data-ttu-id="799f4-126">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="799f4-126">Required.</span></span> <span data-ttu-id="799f4-127">Elenco di costanti membro dichiarato nella presente informativa.</span><span class="sxs-lookup"><span data-stu-id="799f4-127">List of member constants being declared in this statement.</span></span> <span data-ttu-id="799f4-128">Più membri vengono visualizzati in righe di codice sorgente singoli.</span><span class="sxs-lookup"><span data-stu-id="799f4-128">Multiple members appear on individual source code lines.</span></span>  
  
     <span data-ttu-id="799f4-129">Ogni `member` presenta la sintassi e le parti seguenti:`[<attribute list>] member name [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="799f4-129">Each `member` has the following syntax and parts: `[<attribute list>] member name [ = initializer ]`</span></span>  
  
    |<span data-ttu-id="799f4-130">Parte</span><span class="sxs-lookup"><span data-stu-id="799f4-130">Part</span></span>|<span data-ttu-id="799f4-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="799f4-131">Description</span></span>|  
    |---|---|  
    |`membername`|<span data-ttu-id="799f4-132">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="799f4-132">Required.</span></span> <span data-ttu-id="799f4-133">Nome del membro.</span><span class="sxs-lookup"><span data-stu-id="799f4-133">Name of this member.</span></span>|  
    |`initializer`|<span data-ttu-id="799f4-134">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="799f4-134">Optional.</span></span> <span data-ttu-id="799f4-135">Espressione che viene valutata in fase di compilazione e assegnata al membro.</span><span class="sxs-lookup"><span data-stu-id="799f4-135">Expression that is evaluated at compile time and assigned to this member.</span></span>|  
  
-   <span data-ttu-id="799f4-136">`End` `Enum`</span><span class="sxs-lookup"><span data-stu-id="799f4-136">`End` `Enum`</span></span>  
  
     <span data-ttu-id="799f4-137">Termina il blocco `Enum`.</span><span class="sxs-lookup"><span data-stu-id="799f4-137">Terminates the `Enum` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="799f4-138">Note</span><span class="sxs-lookup"><span data-stu-id="799f4-138">Remarks</span></span>  
 <span data-ttu-id="799f4-139">Se si dispone di un set di valori non modificabili logicamente correlati tra loro, è possibile definirli insieme in un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="799f4-139">If you have a set of unchanging values that are logically related to each other, you can define them together in an enumeration.</span></span> <span data-ttu-id="799f4-140">Fornisce nomi significativi per l'enumerazione e i relativi membri, che sono più facili da ricordare rispetto ai relativi valori.</span><span class="sxs-lookup"><span data-stu-id="799f4-140">This provides meaningful names for the enumeration and its members, which are easier to remember than their values.</span></span> <span data-ttu-id="799f4-141">È quindi possibile utilizzare i membri di enumerazione in molte posizioni nel codice.</span><span class="sxs-lookup"><span data-stu-id="799f4-141">You can then use the enumeration members in many places in your code.</span></span>  
  
 <span data-ttu-id="799f4-142">Di seguito sono indicati i vantaggi dell'utilizzo di enumerazioni:</span><span class="sxs-lookup"><span data-stu-id="799f4-142">The benefits of using enumerations include the following:</span></span>  
  
-   <span data-ttu-id="799f4-143">Per ridurre gli errori causati dalla trasposizione o digitazione di numeri.</span><span class="sxs-lookup"><span data-stu-id="799f4-143">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
-   <span data-ttu-id="799f4-144">Consente di modificare i valori in futuro.</span><span class="sxs-lookup"><span data-stu-id="799f4-144">Makes it easy to change values in the future.</span></span>  
  
-   <span data-ttu-id="799f4-145">Rende il codice più leggibile, ciò significa che è meno probabile che gli errori verranno introdotte.</span><span class="sxs-lookup"><span data-stu-id="799f4-145">Makes code easier to read, which means it is less likely that errors will be introduced.</span></span>  
  
-   <span data-ttu-id="799f4-146">Garantisce la compatibilità.</span><span class="sxs-lookup"><span data-stu-id="799f4-146">Ensures forward compatibility.</span></span> <span data-ttu-id="799f4-147">Se si utilizzano le enumerazioni, il codice è meno probabile che non venga completata se in futuro un utente modifica i valori corrispondenti ai nomi dei membri.</span><span class="sxs-lookup"><span data-stu-id="799f4-147">If you use enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
 <span data-ttu-id="799f4-148">Un'enumerazione ha un nome, tipo di dati sottostante e un set di membri.</span><span class="sxs-lookup"><span data-stu-id="799f4-148">An enumeration has a name, an underlying data type, and a set of members.</span></span> <span data-ttu-id="799f4-149">Ogni membro rappresenta una costante.</span><span class="sxs-lookup"><span data-stu-id="799f4-149">Each member represents a constant.</span></span>  
  
 <span data-ttu-id="799f4-150">Un'enumerazione dichiarata a livello di classe, struttura, modulo o interfaccia, all'esterno di qualsiasi routine, è un *enumerazione membro*.</span><span class="sxs-lookup"><span data-stu-id="799f4-150">An enumeration declared at class, structure, module, or interface level, outside any procedure, is a *member enumeration*.</span></span> <span data-ttu-id="799f4-151">È un membro della classe, struttura, modulo o interfaccia che lo dichiara.</span><span class="sxs-lookup"><span data-stu-id="799f4-151">It is a member of the class, structure, module, or interface that declares it.</span></span>  
  
 <span data-ttu-id="799f4-152">Le enumerazioni di membri è possibile accedere da qualsiasi loro classe, struttura, modulo o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="799f4-152">Member enumerations can be accessed from anywhere within their class, structure, module, or interface.</span></span> <span data-ttu-id="799f4-153">Codice esterno di una classe, struttura o un modulo necessario qualificare il nome di un'enumerazione di membri con il nome di tale classe, struttura o un modulo.</span><span class="sxs-lookup"><span data-stu-id="799f4-153">Code outside a class, structure, or module must qualify a member enumeration's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="799f4-154">È possibile evitare la necessità di utilizzare nomi completi mediante l'aggiunta di un [importazioni](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) istruzione per il file di origine.</span><span class="sxs-lookup"><span data-stu-id="799f4-154">You can avoid the need to use fully qualified names by adding an [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statement to the source file.</span></span>  
  
 <span data-ttu-id="799f4-155">Un'enumerazione dichiarata a livello di spazio dei nomi, all'esterno di qualsiasi classe, struttura, modulo o interfaccia, è un membro dello spazio dei nomi in cui è presente.</span><span class="sxs-lookup"><span data-stu-id="799f4-155">An enumeration declared at namespace level, outside any class, structure, module, or interface, is a member of the namespace in which it appears.</span></span>  
  
 <span data-ttu-id="799f4-156">Il *contesto della dichiarazione* per un'enumerazione deve essere un file di origine, lo spazio dei nomi, classe, struttura, modulo o interfaccia e non può essere una routine.</span><span class="sxs-lookup"><span data-stu-id="799f4-156">The *declaration context* for an enumeration must be a source file, namespace, class, structure, module, or interface, and cannot be a procedure.</span></span> <span data-ttu-id="799f4-157">Per ulteriori informazioni, vedere [contesti delle dichiarazioni e livelli di accesso predefinito](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="799f4-157">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="799f4-158">È possibile applicare attributi a un'enumerazione nel suo complesso, ma non ai relativi membri singolarmente.</span><span class="sxs-lookup"><span data-stu-id="799f4-158">You can apply attributes to an enumeration as a whole, but not to its members individually.</span></span> <span data-ttu-id="799f4-159">Un attributo fornisce informazioni per i metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="799f4-159">An attribute contributes information to the assembly's metadata.</span></span>  
  
## <a name="data-type"></a><span data-ttu-id="799f4-160">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="799f4-160">Data Type</span></span>  
 <span data-ttu-id="799f4-161">Il `Enum` istruzione può dichiarare il tipo di dati di un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="799f4-161">The `Enum` statement can declare the data type of an enumeration.</span></span> <span data-ttu-id="799f4-162">Ciascun membro viene attribuito il tipo di dati dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="799f4-162">Each member takes the enumeration's data type.</span></span> <span data-ttu-id="799f4-163">You can specify `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort`.</span><span class="sxs-lookup"><span data-stu-id="799f4-163">You can specify `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort`.</span></span>  
  
 <span data-ttu-id="799f4-164">Se non si specifica `datatype` per l'enumerazione, ogni membro viene attribuito il tipo di dati relativo `initializer`.</span><span class="sxs-lookup"><span data-stu-id="799f4-164">If you do not specify `datatype` for the enumeration, each member takes the data type of its `initializer`.</span></span> <span data-ttu-id="799f4-165">Se si specificano entrambe `datatype` e `initializer`, il tipo di dati `initializer` deve essere convertibile in `datatype`.</span><span class="sxs-lookup"><span data-stu-id="799f4-165">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="799f4-166">Se non si specifica `datatype` né `initializer` è presente, il tipo di dati il valore predefinito è `Integer`.</span><span class="sxs-lookup"><span data-stu-id="799f4-166">If neither `datatype` nor `initializer` is present, the data type defaults to `Integer`.</span></span>  
  
## <a name="initializing-members"></a><span data-ttu-id="799f4-167">Inizializzazione dei membri</span><span class="sxs-lookup"><span data-stu-id="799f4-167">Initializing Members</span></span>  
 <span data-ttu-id="799f4-168">Il `Enum` istruzione possibile inizializzare il contenuto di membri selezionati in `memberlist`.</span><span class="sxs-lookup"><span data-stu-id="799f4-168">The `Enum` statement can initialize the contents of selected members in `memberlist`.</span></span> <span data-ttu-id="799f4-169">Utilizzare `initializer` per fornire un'espressione da assegnare al membro.</span><span class="sxs-lookup"><span data-stu-id="799f4-169">You use `initializer` to supply an expression to be assigned to the member.</span></span>  
  
 <span data-ttu-id="799f4-170">Se non si specifica `initializer` per un membro, Visual Basic inizializzato su zero (se è il primo `member` in `memberlist`), o su un valore maggiore di quello che di immediatamente precedente `member`.</span><span class="sxs-lookup"><span data-stu-id="799f4-170">If you do not specify `initializer` for a member, Visual Basic initializes it either to zero (if it is the first `member` in `memberlist`), or to a value greater by one than that of the immediately preceding `member`.</span></span>  
  
 <span data-ttu-id="799f4-171">L'espressione fornita in ciascun `initializer` può essere qualsiasi combinazione di valori letterali, altre costanti che sono già definiti e membri di enumerazione che sono già definiti, incluso un membro precedente di questa enumerazione.</span><span class="sxs-lookup"><span data-stu-id="799f4-171">The expression supplied in each `initializer` can be any combination of literals, other constants that are already defined, and enumeration members that are already defined, including a previous member of this enumeration.</span></span> <span data-ttu-id="799f4-172">È possibile utilizzare gli operatori aritmetici e logici per combinare tali elementi.</span><span class="sxs-lookup"><span data-stu-id="799f4-172">You can use arithmetic and logical operators to combine such elements.</span></span>  
  
 <span data-ttu-id="799f4-173">Non è possibile utilizzare variabili o funzioni `initializer`.</span><span class="sxs-lookup"><span data-stu-id="799f4-173">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="799f4-174">Tuttavia, è possibile utilizzare parole chiave di conversione, ad esempio `CByte` e `CShort`.</span><span class="sxs-lookup"><span data-stu-id="799f4-174">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="799f4-175">È inoltre possibile utilizzare `AscW` se viene chiamata con una costante `String` o `Char` argomento, dal momento che può essere valutata in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="799f4-175">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>  
  
 <span data-ttu-id="799f4-176">Le enumerazioni non possono avere valori a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="799f4-176">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="799f4-177">Se un membro viene assegnato un valore a virgola mobile e `Option Strict` è impostata su on, si verifica un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="799f4-177">If a member is assigned a floating-point value and `Option Strict` is set to on, a compiler error occurs.</span></span> <span data-ttu-id="799f4-178">Se `Option Strict` è disattivata, il valore viene convertito automaticamente nel `Enum` tipo.</span><span class="sxs-lookup"><span data-stu-id="799f4-178">If `Option Strict` is off, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="799f4-179">Se il valore di un membro supera l'intervallo consentito per il tipo di dati sottostante o se si inizializza un membro del valore massimo consentito dal tipo di dati sottostante, il compilatore segnala un errore.</span><span class="sxs-lookup"><span data-stu-id="799f4-179">If the value of a member exceeds the allowable range for the underlying data type, or if you initialize any member to the maximum value allowed by the underlying data type, the compiler reports an error.</span></span>  
  
## <a name="modifiers"></a><span data-ttu-id="799f4-180">Modificatori</span><span class="sxs-lookup"><span data-stu-id="799f4-180">Modifiers</span></span>  
 <span data-ttu-id="799f4-181">Classe, struttura, modulo e predefinito enumerazioni membro di interfaccia di accesso pubblico.</span><span class="sxs-lookup"><span data-stu-id="799f4-181">Class, structure, module, and interface member enumerations default to public access.</span></span> <span data-ttu-id="799f4-182">È possibile regolare i livelli di accesso con i modificatori di accesso.</span><span class="sxs-lookup"><span data-stu-id="799f4-182">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="799f4-183">Namespace membro enumerazioni per impostazione predefinita l'accesso friend.</span><span class="sxs-lookup"><span data-stu-id="799f4-183">Namespace member enumerations default to friend access.</span></span> <span data-ttu-id="799f4-184">È possibile regolare i livelli di accesso pubblico, ma non per privati o protetti.</span><span class="sxs-lookup"><span data-stu-id="799f4-184">You can adjust their access levels to public, but not to private or protected.</span></span> <span data-ttu-id="799f4-185">Per ulteriori informazioni, vedere [livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="799f4-185">For more information, see [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="799f4-186">Tutti i membri di enumerazione dispongono di accesso pubblico e non è possibile utilizzare i modificatori di accesso su di essi.</span><span class="sxs-lookup"><span data-stu-id="799f4-186">All enumeration members have public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="799f4-187">Tuttavia, se l'enumerazione dispone di un livello di accesso più limitato, il livello di accesso di enumerazione specificato ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="799f4-187">However, if the enumeration itself has a more restricted access level, the specified enumeration access level takes precedence.</span></span>  
  
 <span data-ttu-id="799f4-188">Per impostazione predefinita, tutte le enumerazioni sono tipi e i campi sono costanti.</span><span class="sxs-lookup"><span data-stu-id="799f4-188">By default, all enumerations are types and their fields are constants.</span></span> <span data-ttu-id="799f4-189">Pertanto il `Shared`, `Static`, e `ReadOnly` le parole chiave non possono essere utilizzate quando si dichiara un'enumerazione o i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="799f4-189">Therefore the `Shared`, `Static`, and `ReadOnly` keywords cannot be used when declaring an enumeration or its members.</span></span>  
  
## <a name="assigning-multiple-values"></a><span data-ttu-id="799f4-190">L'assegnazione di più valori</span><span class="sxs-lookup"><span data-stu-id="799f4-190">Assigning Multiple Values</span></span>  
 <span data-ttu-id="799f4-191">Enumerazioni rappresentano in genere valori si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="799f4-191">Enumerations typically represent mutually exclusive values.</span></span> <span data-ttu-id="799f4-192">Includendo il <xref:System.FlagsAttribute>attributo il `Enum` dichiarazione, è possibile invece assegnare più valori a un'istanza dell'enumerazione.</xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="799f4-192">By including the <xref:System.FlagsAttribute> attribute in the `Enum` declaration, you can instead assign multiple values to an instance of the enumeration.</span></span> <span data-ttu-id="799f4-193">Il <xref:System.FlagsAttribute>attributo specifica che l'enumerazione vengono considerati come un campo di bit, ovvero un set di flag.</xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="799f4-193">The <xref:System.FlagsAttribute> attribute specifies that the enumeration be treated as a bit field, that is, a set of flags.</span></span> <span data-ttu-id="799f4-194">Questi sono denominati *bit per bit* enumerazioni.</span><span class="sxs-lookup"><span data-stu-id="799f4-194">These are called *bitwise* enumerations.</span></span>  
  
 <span data-ttu-id="799f4-195">Quando si dichiara un'enumerazione tramite il <xref:System.FlagsAttribute>attributo, si consiglia di utilizzare potenze di 2, ovvero, 1, 2, 4, 8, 16 e così via, per i valori.</xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="799f4-195">When you declare an enumeration by using the <xref:System.FlagsAttribute> attribute, we recommend that you use powers of 2, that is, 1, 2, 4, 8, 16, and so on, for the values.</span></span> <span data-ttu-id="799f4-196">È inoltre consigliabile "None" il nome di un membro il cui valore è 0.</span><span class="sxs-lookup"><span data-stu-id="799f4-196">We also recommend that "None" be the name of a member whose value is 0.</span></span> <span data-ttu-id="799f4-197">Per ulteriori istruzioni, vedere <xref:System.FlagsAttribute>e <xref:System.Enum>.</xref:System.Enum> </xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="799f4-197">For additional guidelines, see <xref:System.FlagsAttribute> and <xref:System.Enum>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="799f4-198">Esempio</span><span class="sxs-lookup"><span data-stu-id="799f4-198">Example</span></span>  
 <span data-ttu-id="799f4-199">Nell'esempio seguente viene illustrato come utilizzare il `Enum` istruzione.</span><span class="sxs-lookup"><span data-stu-id="799f4-199">The following example shows how to use the `Enum` statement.</span></span> <span data-ttu-id="799f4-200">Si noti che il membro è detto `EggSizeEnum.Medium`e non come `Medium`.</span><span class="sxs-lookup"><span data-stu-id="799f4-200">Note that the member is referred to as `EggSizeEnum.Medium`, and not as `Medium`.</span></span>  
  
 <span data-ttu-id="799f4-201">[!code-vb[VbEnumsTask n.&41;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="799f4-201">[!code-vb[VbEnumsTask#41](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="799f4-202">Esempio</span><span class="sxs-lookup"><span data-stu-id="799f4-202">Example</span></span>  
 <span data-ttu-id="799f4-203">Nell'esempio seguente il metodo non è compreso il `Egg` (classe).</span><span class="sxs-lookup"><span data-stu-id="799f4-203">The method in the following example is outside the `Egg` class.</span></span> <span data-ttu-id="799f4-204">Di conseguenza, `EggSizeEnum` nome completo come `Egg.EggSizeEnum`.</span><span class="sxs-lookup"><span data-stu-id="799f4-204">Therefore, `EggSizeEnum` is fully qualified as `Egg.EggSizeEnum`.</span></span>  
  
 <span data-ttu-id="799f4-205">[!code-vb[VbEnumsTask&#42;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="799f4-205">[!code-vb[VbEnumsTask#42](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="799f4-206">Esempio</span><span class="sxs-lookup"><span data-stu-id="799f4-206">Example</span></span>  
 <span data-ttu-id="799f4-207">Nell'esempio seguente viene utilizzata la `Enum` istruzione per definire un set correlato di valori costanti denominati.</span><span class="sxs-lookup"><span data-stu-id="799f4-207">The following example uses the `Enum` statement to define a related set of named constant values.</span></span> <span data-ttu-id="799f4-208">In questo caso, i valori sono i colori, che è possibile scegliere di progettare il form di immissione di dati per un database.</span><span class="sxs-lookup"><span data-stu-id="799f4-208">In this case, the values are colors you might choose to design data entry forms for a database.</span></span>  
  
 <span data-ttu-id="799f4-209">[!code-vb[&#30; VbEnumsTask](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="799f4-209">[!code-vb[VbEnumsTask#30](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="799f4-210">Esempio</span><span class="sxs-lookup"><span data-stu-id="799f4-210">Example</span></span>  
 <span data-ttu-id="799f4-211">Nell'esempio seguente vengono illustrati i valori che includono numeri positivi e negativi.</span><span class="sxs-lookup"><span data-stu-id="799f4-211">The following example shows values that include both positive and negative numbers.</span></span>  
  
 <span data-ttu-id="799f4-212">[!code-vb[VbEnumsTask&#31;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="799f4-212">[!code-vb[VbEnumsTask#31](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_4.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="799f4-213">Esempio</span><span class="sxs-lookup"><span data-stu-id="799f4-213">Example</span></span>  
 <span data-ttu-id="799f4-214">Nell'esempio seguente, un `As` clausola viene utilizzata per specificare il `datatype` di un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="799f4-214">In the following example, an `As` clause is used to specify the `datatype` of an enumeration.</span></span>  
  
 <span data-ttu-id="799f4-215">[!code-vb[6 VbEnumsTask](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="799f4-215">[!code-vb[VbEnumsTask#6](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_5.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="799f4-216">Esempio</span><span class="sxs-lookup"><span data-stu-id="799f4-216">Example</span></span>  
 <span data-ttu-id="799f4-217">Nell'esempio seguente viene illustrato come utilizzare un'enumerazione bit per bit.</span><span class="sxs-lookup"><span data-stu-id="799f4-217">The following example shows how to use a bitwise enumeration.</span></span> <span data-ttu-id="799f4-218">Più valori possono essere assegnati a un'istanza di un'enumerazione bit per bit.</span><span class="sxs-lookup"><span data-stu-id="799f4-218">Multiple values can be assigned to an instance of a bitwise enumeration.</span></span> <span data-ttu-id="799f4-219">Il `Enum` dichiarazione include il <xref:System.FlagsAttribute>attributo, che indica che l'enumerazione può essere considerato come un set di flag.</xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="799f4-219">The `Enum` declaration includes the <xref:System.FlagsAttribute> attribute, which indicates that the enumeration can be treated as a set of flags.</span></span>  
  
 <span data-ttu-id="799f4-220">[!code-vb[VbEnumsTask n.&61;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="799f4-220">[!code-vb[VbEnumsTask#61](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_6.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="799f4-221">Esempio</span><span class="sxs-lookup"><span data-stu-id="799f4-221">Example</span></span>  
 <span data-ttu-id="799f4-222">Nell'esempio seguente scorre un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="799f4-222">The following example iterates through an enumeration.</span></span> <span data-ttu-id="799f4-223">Usa il <xref:System.Enum.GetNames%2A>per recuperare una matrice di nomi di membro dell'enumerazione e <xref:System.Enum.GetValues%2A>per recuperare una matrice di valori del membro.</xref:System.Enum.GetValues%2A> </xref:System.Enum.GetNames%2A></span><span class="sxs-lookup"><span data-stu-id="799f4-223">It uses the <xref:System.Enum.GetNames%2A> method to retrieve an array of member names from the enumeration, and <xref:System.Enum.GetValues%2A> to retrieve an array of member values.</span></span>  
  
 <span data-ttu-id="799f4-224">[!code-vb[51 VbEnumsTask](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="799f4-224">[!code-vb[VbEnumsTask#51](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_7.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="799f4-225">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="799f4-225">See Also</span></span>  
 <span data-ttu-id="799f4-226"><xref:System.Enum></xref:System.Enum></span><span class="sxs-lookup"><span data-stu-id="799f4-226"><xref:System.Enum></span></span>   
 <span data-ttu-id="799f4-227"><xref:Microsoft.VisualBasic.Strings.AscW%2A></xref:Microsoft.VisualBasic.Strings.AscW%2A></span><span class="sxs-lookup"><span data-stu-id="799f4-227"><xref:Microsoft.VisualBasic.Strings.AscW%2A></span></span>   
<span data-ttu-id="799f4-228"> [Const (istruzione)](../../../visual-basic/language-reference/statements/const-statement.md) </span><span class="sxs-lookup"><span data-stu-id="799f4-228"> [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) </span></span>  
<span data-ttu-id="799f4-229"> [Dim (istruzione)](../../../visual-basic/language-reference/statements/dim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="799f4-229"> [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) </span></span>  
<span data-ttu-id="799f4-230"> [Conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="799f4-230"> [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span></span>  
<span data-ttu-id="799f4-231"> [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span><span class="sxs-lookup"><span data-stu-id="799f4-231"> [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span></span>  
<span data-ttu-id="799f4-232"> [Costanti ed enumerazioni](../../../visual-basic/language-reference/constants-and-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="799f4-232"> [Constants and Enumerations](../../../visual-basic/language-reference/constants-and-enumerations.md)</span></span>
