---
title: Istruzione Enum
ms.date: 07/20/2015
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
ms.openlocfilehash: 976cc68d67c69ec86918962ab2dd3406d15aed9a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404732"
---
# <a name="enum-statement-visual-basic"></a><span data-ttu-id="281b7-102">Istruzione Enum (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="281b7-102">Enum Statement (Visual Basic)</span></span>

<span data-ttu-id="281b7-103">Dichiara un'enumerazione e definisce i valori dei relativi membri.</span><span class="sxs-lookup"><span data-stu-id="281b7-103">Declares an enumeration and defines the values of its members.</span></span>

## <a name="syntax"></a><span data-ttu-id="281b7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="281b7-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]
Enum enumerationname [ As datatype ]
   memberlist
End Enum
```

## <a name="parts"></a><span data-ttu-id="281b7-105">Parti</span><span class="sxs-lookup"><span data-stu-id="281b7-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="281b7-106">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="281b7-106">Optional.</span></span> <span data-ttu-id="281b7-107">Elenco degli attributi che si applicano a questa enumerazione.</span><span class="sxs-lookup"><span data-stu-id="281b7-107">List of attributes that apply to this enumeration.</span></span> <span data-ttu-id="281b7-108">È necessario racchiudere l' [elenco degli attributi](attribute-list.md) tra parentesi angolari (" `<` " e " `>` ").</span><span class="sxs-lookup"><span data-stu-id="281b7-108">You must enclose the [attribute list](attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>

  <span data-ttu-id="281b7-109">L' <xref:System.FlagsAttribute> attributo indica che il valore di un'istanza dell'enumerazione può includere più membri di enumerazione e che ogni membro rappresenta un campo di bit nel valore di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="281b7-109">The <xref:System.FlagsAttribute> attribute indicates that the value of an instance of the enumeration can include multiple enumeration members, and that each member represents a bit field in the enumeration value.</span></span>

- `accessmodifier`

  <span data-ttu-id="281b7-110">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="281b7-110">Optional.</span></span> <span data-ttu-id="281b7-111">Specifica il codice che può accedere a questa enumerazione.</span><span class="sxs-lookup"><span data-stu-id="281b7-111">Specifies what code can access this enumeration.</span></span> <span data-ttu-id="281b7-112">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="281b7-112">Can be one of the following:</span></span>

  - [<span data-ttu-id="281b7-113">Pubblica</span><span class="sxs-lookup"><span data-stu-id="281b7-113">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="281b7-114">Protetto</span><span class="sxs-lookup"><span data-stu-id="281b7-114">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="281b7-115">Amico</span><span class="sxs-lookup"><span data-stu-id="281b7-115">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="281b7-116">Privata</span><span class="sxs-lookup"><span data-stu-id="281b7-116">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="281b7-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="281b7-117">Protected Friend</span></span>](../modifiers/protected-friend.md)

  - [<span data-ttu-id="281b7-118">Privato protetto</span><span class="sxs-lookup"><span data-stu-id="281b7-118">Private Protected</span></span>](../modifiers/private-protected.md)

- `Shadows`

  <span data-ttu-id="281b7-119">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="281b7-119">Optional.</span></span> <span data-ttu-id="281b7-120">Specifica che questa enumerazione dichiara e nasconde un elemento di programmazione con nome identico o un set di elementi in overload in una classe base.</span><span class="sxs-lookup"><span data-stu-id="281b7-120">Specifies that this enumeration redeclares and hides an identically named programming element, or set of overloaded elements, in a base class.</span></span> <span data-ttu-id="281b7-121">È possibile specificare le [ombreggiature](../modifiers/shadows.md) solo sull'enumerazione stessa, non su nessuno dei relativi membri.</span><span class="sxs-lookup"><span data-stu-id="281b7-121">You can specify [Shadows](../modifiers/shadows.md) only on the enumeration itself, not on any of its members.</span></span>

- `enumerationname`

  <span data-ttu-id="281b7-122">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="281b7-122">Required.</span></span> <span data-ttu-id="281b7-123">Nome dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="281b7-123">Name of the enumeration.</span></span> <span data-ttu-id="281b7-124">Per informazioni sui nomi validi, vedere [nomi di elementi dichiarati](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="281b7-124">For information on valid names, see [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `datatype`

  <span data-ttu-id="281b7-125">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="281b7-125">Optional.</span></span> <span data-ttu-id="281b7-126">Tipo di dati dell'enumerazione e di tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="281b7-126">Data type of the enumeration and all its members.</span></span>

- `memberlist`

  <span data-ttu-id="281b7-127">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="281b7-127">Required.</span></span> <span data-ttu-id="281b7-128">Elenco di costanti membro dichiarate in questa istruzione.</span><span class="sxs-lookup"><span data-stu-id="281b7-128">List of member constants being declared in this statement.</span></span> <span data-ttu-id="281b7-129">Vengono visualizzati più membri nelle singole righe del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="281b7-129">Multiple members appear on individual source code lines.</span></span>

  <span data-ttu-id="281b7-130">Ognuno `member` presenta la sintassi e le parti seguenti:`[<attribute list>] member name [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="281b7-130">Each `member` has the following syntax and parts: `[<attribute list>] member name [ = initializer ]`</span></span>

  |<span data-ttu-id="281b7-131">Parte</span><span class="sxs-lookup"><span data-stu-id="281b7-131">Part</span></span>|<span data-ttu-id="281b7-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="281b7-132">Description</span></span>|
  |---|---|
  |`membername`|<span data-ttu-id="281b7-133">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="281b7-133">Required.</span></span> <span data-ttu-id="281b7-134">Nome del membro.</span><span class="sxs-lookup"><span data-stu-id="281b7-134">Name of this member.</span></span>|
  |`initializer`|<span data-ttu-id="281b7-135">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="281b7-135">Optional.</span></span> <span data-ttu-id="281b7-136">Espressione valutata in fase di compilazione e assegnata a questo membro.</span><span class="sxs-lookup"><span data-stu-id="281b7-136">Expression that is evaluated at compile time and assigned to this member.</span></span>|

- <span data-ttu-id="281b7-137">`End` `Enum`</span><span class="sxs-lookup"><span data-stu-id="281b7-137">`End` `Enum`</span></span>

  <span data-ttu-id="281b7-138">Termina il blocco `Enum`.</span><span class="sxs-lookup"><span data-stu-id="281b7-138">Terminates the `Enum` block.</span></span>

## <a name="remarks"></a><span data-ttu-id="281b7-139">Commenti</span><span class="sxs-lookup"><span data-stu-id="281b7-139">Remarks</span></span>

<span data-ttu-id="281b7-140">Se si dispone di un set di valori non modificabili logicamente correlati tra loro, è possibile definirli insieme in un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="281b7-140">If you have a set of unchanging values that are logically related to each other, you can define them together in an enumeration.</span></span> <span data-ttu-id="281b7-141">Che fornisce nomi significativi per l'enumerazione e i relativi membri, che sono più facili da ricordare rispetto ai relativi valori.</span><span class="sxs-lookup"><span data-stu-id="281b7-141">This provides meaningful names for the enumeration and its members, which are easier to remember than their values.</span></span> <span data-ttu-id="281b7-142">È quindi possibile usare i membri di enumerazione in molte posizioni nel codice.</span><span class="sxs-lookup"><span data-stu-id="281b7-142">You can then use the enumeration members in many places in your code.</span></span>

<span data-ttu-id="281b7-143">I vantaggi dell'utilizzo delle enumerazioni includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="281b7-143">The benefits of using enumerations include the following:</span></span>

- <span data-ttu-id="281b7-144">Riduce gli errori causati dalla trasposizione o dalla digitazione errata dei numeri.</span><span class="sxs-lookup"><span data-stu-id="281b7-144">Reduces errors caused by transposing or mistyping numbers.</span></span>

- <span data-ttu-id="281b7-145">Semplifica la modifica dei valori in futuro.</span><span class="sxs-lookup"><span data-stu-id="281b7-145">Makes it easy to change values in the future.</span></span>

- <span data-ttu-id="281b7-146">Semplifica la lettura del codice, il che significa che è meno probabile che vengano introdotti errori.</span><span class="sxs-lookup"><span data-stu-id="281b7-146">Makes code easier to read, which means it is less likely that errors will be introduced.</span></span>

- <span data-ttu-id="281b7-147">Garantisce la compatibilità con le edizioni.</span><span class="sxs-lookup"><span data-stu-id="281b7-147">Ensures forward compatibility.</span></span> <span data-ttu-id="281b7-148">Se si utilizzano le enumerazioni, è meno probabile che il codice abbia esito negativo se in futuro qualcuno modifica i valori corrispondenti ai nomi dei membri.</span><span class="sxs-lookup"><span data-stu-id="281b7-148">If you use enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>

<span data-ttu-id="281b7-149">Un'enumerazione ha un nome, un tipo di dati sottostante e un set di membri.</span><span class="sxs-lookup"><span data-stu-id="281b7-149">An enumeration has a name, an underlying data type, and a set of members.</span></span> <span data-ttu-id="281b7-150">Ogni membro rappresenta una costante.</span><span class="sxs-lookup"><span data-stu-id="281b7-150">Each member represents a constant.</span></span>

<span data-ttu-id="281b7-151">Un'enumerazione dichiarata a livello di classe, struttura, modulo o interfaccia, all'esterno di qualsiasi routine, è un' *enumerazione di membri*.</span><span class="sxs-lookup"><span data-stu-id="281b7-151">An enumeration declared at class, structure, module, or interface level, outside any procedure, is a *member enumeration*.</span></span> <span data-ttu-id="281b7-152">È un membro della classe, struttura, modulo o interfaccia che lo dichiara.</span><span class="sxs-lookup"><span data-stu-id="281b7-152">It is a member of the class, structure, module, or interface that declares it.</span></span>

<span data-ttu-id="281b7-153">È possibile accedere alle enumerazioni dei membri da qualsiasi posizione all'interno della classe, struttura, modulo o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="281b7-153">Member enumerations can be accessed from anywhere within their class, structure, module, or interface.</span></span> <span data-ttu-id="281b7-154">Il codice esterno a una classe, una struttura o un modulo deve qualificare il nome di un'enumerazione membro con il nome della classe, della struttura o del modulo.</span><span class="sxs-lookup"><span data-stu-id="281b7-154">Code outside a class, structure, or module must qualify a member enumeration's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="281b7-155">Per evitare di dover utilizzare nomi completi, è possibile aggiungere un'istruzione [Imports](imports-statement-net-namespace-and-type.md) al file di origine.</span><span class="sxs-lookup"><span data-stu-id="281b7-155">You can avoid the need to use fully qualified names by adding an [Imports](imports-statement-net-namespace-and-type.md) statement to the source file.</span></span>

<span data-ttu-id="281b7-156">Un'enumerazione dichiarata a livello di spazio dei nomi, all'esterno di qualsiasi classe, struttura, modulo o interfaccia, è un membro dello spazio dei nomi in cui viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="281b7-156">An enumeration declared at namespace level, outside any class, structure, module, or interface, is a member of the namespace in which it appears.</span></span>

<span data-ttu-id="281b7-157">Il *contesto di dichiarazione* per un'enumerazione deve essere un file di origine, uno spazio dei nomi, una classe, una struttura, un modulo o un'interfaccia e non può essere una routine.</span><span class="sxs-lookup"><span data-stu-id="281b7-157">The *declaration context* for an enumeration must be a source file, namespace, class, structure, module, or interface, and cannot be a procedure.</span></span> <span data-ttu-id="281b7-158">Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="281b7-158">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="281b7-159">È possibile applicare gli attributi a un'enumerazione nel suo complesso, ma non ai relativi membri singolarmente.</span><span class="sxs-lookup"><span data-stu-id="281b7-159">You can apply attributes to an enumeration as a whole, but not to its members individually.</span></span> <span data-ttu-id="281b7-160">Un attributo fornisce informazioni ai metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="281b7-160">An attribute contributes information to the assembly's metadata.</span></span>

## <a name="data-type"></a><span data-ttu-id="281b7-161">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="281b7-161">Data Type</span></span>

<span data-ttu-id="281b7-162">L' `Enum` istruzione può dichiarare il tipo di dati di un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="281b7-162">The `Enum` statement can declare the data type of an enumeration.</span></span> <span data-ttu-id="281b7-163">Ogni membro accetta il tipo di dati dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="281b7-163">Each member takes the enumeration's data type.</span></span> <span data-ttu-id="281b7-164">È possibile specificare `Byte` , `Integer` , `Long` , `SByte` , `Short` , `UInteger` , `ULong` o `UShort` .</span><span class="sxs-lookup"><span data-stu-id="281b7-164">You can specify `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort`.</span></span>

<span data-ttu-id="281b7-165">Se non si specifica `datatype` per l'enumerazione, ogni membro accetta il tipo di dati del relativo oggetto `initializer` .</span><span class="sxs-lookup"><span data-stu-id="281b7-165">If you do not specify `datatype` for the enumeration, each member takes the data type of its `initializer`.</span></span> <span data-ttu-id="281b7-166">Se si specificano sia `datatype` che `initializer` , il tipo di dati di `initializer` deve essere convertibile in `datatype` .</span><span class="sxs-lookup"><span data-stu-id="281b7-166">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="281b7-167">Se né `datatype` né `initializer` sono presenti, il tipo di dati predefinito è `Integer` .</span><span class="sxs-lookup"><span data-stu-id="281b7-167">If neither `datatype` nor `initializer` is present, the data type defaults to `Integer`.</span></span>

## <a name="initializing-members"></a><span data-ttu-id="281b7-168">Inizializzazione di membri</span><span class="sxs-lookup"><span data-stu-id="281b7-168">Initializing Members</span></span>

<span data-ttu-id="281b7-169">L' `Enum` istruzione consente di inizializzare il contenuto dei membri selezionati in `memberlist` .</span><span class="sxs-lookup"><span data-stu-id="281b7-169">The `Enum` statement can initialize the contents of selected members in `memberlist`.</span></span> <span data-ttu-id="281b7-170">Usare `initializer` per fornire un'espressione da assegnare al membro.</span><span class="sxs-lookup"><span data-stu-id="281b7-170">You use `initializer` to supply an expression to be assigned to the member.</span></span>

<span data-ttu-id="281b7-171">Se non si specifica `initializer` per un membro, Visual Basic lo inizializza su zero (se è il primo `member` in `memberlist` ) o su un valore maggiore di uno rispetto a quello dell'oggetto immediatamente precedente `member` .</span><span class="sxs-lookup"><span data-stu-id="281b7-171">If you do not specify `initializer` for a member, Visual Basic initializes it either to zero (if it is the first `member` in `memberlist`), or to a value greater by one than that of the immediately preceding `member`.</span></span>

<span data-ttu-id="281b7-172">L'espressione fornita in ogni `initializer` può essere costituita da qualsiasi combinazione di valori letterali, altre costanti già definite e membri di enumerazione già definiti, incluso un membro precedente di questa enumerazione.</span><span class="sxs-lookup"><span data-stu-id="281b7-172">The expression supplied in each `initializer` can be any combination of literals, other constants that are already defined, and enumeration members that are already defined, including a previous member of this enumeration.</span></span> <span data-ttu-id="281b7-173">Per combinare tali elementi, è possibile utilizzare operatori aritmetici e logici.</span><span class="sxs-lookup"><span data-stu-id="281b7-173">You can use arithmetic and logical operators to combine such elements.</span></span>

<span data-ttu-id="281b7-174">Non è possibile usare variabili o funzioni in `initializer` .</span><span class="sxs-lookup"><span data-stu-id="281b7-174">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="281b7-175">Tuttavia, è possibile usare parole chiave di conversione, ad esempio `CByte` e `CShort` .</span><span class="sxs-lookup"><span data-stu-id="281b7-175">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="281b7-176">È anche possibile usare `AscW` se lo si chiama con una costante `String` o un `Char` argomento, poiché può essere valutato in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="281b7-176">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>

<span data-ttu-id="281b7-177">Le enumerazioni non possono avere valori a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="281b7-177">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="281b7-178">Se a un membro viene assegnato un valore a virgola mobile ed `Option Strict` è impostato su on, si verifica un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="281b7-178">If a member is assigned a floating-point value and `Option Strict` is set to on, a compiler error occurs.</span></span> <span data-ttu-id="281b7-179">Se `Option Strict` è off, il valore viene convertito automaticamente nel `Enum` tipo.</span><span class="sxs-lookup"><span data-stu-id="281b7-179">If `Option Strict` is off, the value is automatically converted to the `Enum` type.</span></span>

<span data-ttu-id="281b7-180">Se il valore di un membro supera l'intervallo consentito per il tipo di dati sottostante o se si Inizializza un membro sul valore massimo consentito dal tipo di dati sottostante, il compilatore segnala un errore.</span><span class="sxs-lookup"><span data-stu-id="281b7-180">If the value of a member exceeds the allowable range for the underlying data type, or if you initialize any member to the maximum value allowed by the underlying data type, the compiler reports an error.</span></span>

## <a name="modifiers"></a><span data-ttu-id="281b7-181">Modificatori</span><span class="sxs-lookup"><span data-stu-id="281b7-181">Modifiers</span></span>

<span data-ttu-id="281b7-182">Per impostazione predefinita, le enumerazioni di membri di classe, struttura, modulo e interfaccia sono di accesso pubblico.</span><span class="sxs-lookup"><span data-stu-id="281b7-182">Class, structure, module, and interface member enumerations default to public access.</span></span> <span data-ttu-id="281b7-183">È possibile modificare i livelli di accesso con i modificatori di accesso.</span><span class="sxs-lookup"><span data-stu-id="281b7-183">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="281b7-184">Per impostazione predefinita, le enumerazioni di membri dello spazio dei nomi sono Friend.</span><span class="sxs-lookup"><span data-stu-id="281b7-184">Namespace member enumerations default to friend access.</span></span> <span data-ttu-id="281b7-185">È possibile modificare i livelli di accesso in pubblico, ma non in privato o protetto.</span><span class="sxs-lookup"><span data-stu-id="281b7-185">You can adjust their access levels to public, but not to private or protected.</span></span> <span data-ttu-id="281b7-186">Per altre informazioni, vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="281b7-186">For more information, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="281b7-187">Tutti i membri di enumerazione hanno accesso pubblico e non è possibile usare alcun modificatore di accesso.</span><span class="sxs-lookup"><span data-stu-id="281b7-187">All enumeration members have public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="281b7-188">Tuttavia, se l'enumerazione stessa ha un livello di accesso più limitato, il livello di accesso di enumerazione specificato avrà la precedenza.</span><span class="sxs-lookup"><span data-stu-id="281b7-188">However, if the enumeration itself has a more restricted access level, the specified enumeration access level takes precedence.</span></span>

<span data-ttu-id="281b7-189">Per impostazione predefinita, tutte le enumerazioni sono tipi e i rispettivi campi sono costanti.</span><span class="sxs-lookup"><span data-stu-id="281b7-189">By default, all enumerations are types and their fields are constants.</span></span> <span data-ttu-id="281b7-190">Pertanto `Shared` `Static` `ReadOnly` non è possibile utilizzare le parole chiave, e quando si dichiara un'enumerazione o i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="281b7-190">Therefore the `Shared`, `Static`, and `ReadOnly` keywords cannot be used when declaring an enumeration or its members.</span></span>

## <a name="assigning-multiple-values"></a><span data-ttu-id="281b7-191">Assegnazione di più valori</span><span class="sxs-lookup"><span data-stu-id="281b7-191">Assigning Multiple Values</span></span>

<span data-ttu-id="281b7-192">Le enumerazioni rappresentano in genere valori che si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="281b7-192">Enumerations typically represent mutually exclusive values.</span></span> <span data-ttu-id="281b7-193">Includendo l' <xref:System.FlagsAttribute> attributo nella `Enum` dichiarazione, è invece possibile assegnare più valori a un'istanza dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="281b7-193">By including the <xref:System.FlagsAttribute> attribute in the `Enum` declaration, you can instead assign multiple values to an instance of the enumeration.</span></span> <span data-ttu-id="281b7-194">L' <xref:System.FlagsAttribute> attributo specifica che l'enumerazione deve essere considerata come un campo di bit, ovvero un set di flag.</span><span class="sxs-lookup"><span data-stu-id="281b7-194">The <xref:System.FlagsAttribute> attribute specifies that the enumeration be treated as a bit field, that is, a set of flags.</span></span> <span data-ttu-id="281b7-195">Queste sono denominate enumerazioni *bit per bit* .</span><span class="sxs-lookup"><span data-stu-id="281b7-195">These are called *bitwise* enumerations.</span></span>

<span data-ttu-id="281b7-196">Quando si dichiara un'enumerazione usando l' <xref:System.FlagsAttribute> attributo, è consigliabile usare le potenze di 2, ovvero 1, 2, 4, 8, 16 e così via, per i valori.</span><span class="sxs-lookup"><span data-stu-id="281b7-196">When you declare an enumeration by using the <xref:System.FlagsAttribute> attribute, we recommend that you use powers of 2, that is, 1, 2, 4, 8, 16, and so on, for the values.</span></span> <span data-ttu-id="281b7-197">Si consiglia inoltre che "None" sia il nome di un membro il cui valore è 0.</span><span class="sxs-lookup"><span data-stu-id="281b7-197">We also recommend that "None" be the name of a member whose value is 0.</span></span> <span data-ttu-id="281b7-198">Per ulteriori linee guida, vedere <xref:System.FlagsAttribute> e <xref:System.Enum> .</span><span class="sxs-lookup"><span data-stu-id="281b7-198">For additional guidelines, see <xref:System.FlagsAttribute> and <xref:System.Enum>.</span></span>

## <a name="example"></a><span data-ttu-id="281b7-199">Esempio</span><span class="sxs-lookup"><span data-stu-id="281b7-199">Example</span></span>

<span data-ttu-id="281b7-200">L'esempio seguente mostra come usare l'istruzione `Enum`.</span><span class="sxs-lookup"><span data-stu-id="281b7-200">The following example shows how to use the `Enum` statement.</span></span> <span data-ttu-id="281b7-201">Si noti che il membro è indicato come `EggSizeEnum.Medium` e non come `Medium` .</span><span class="sxs-lookup"><span data-stu-id="281b7-201">Note that the member is referred to as `EggSizeEnum.Medium`, and not as `Medium`.</span></span>

[!code-vb[VbEnumsTask#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#41)]

## <a name="example"></a><span data-ttu-id="281b7-202">Esempio</span><span class="sxs-lookup"><span data-stu-id="281b7-202">Example</span></span>

<span data-ttu-id="281b7-203">Il metodo nell'esempio seguente è esterno alla `Egg` classe.</span><span class="sxs-lookup"><span data-stu-id="281b7-203">The method in the following example is outside the `Egg` class.</span></span> <span data-ttu-id="281b7-204">Pertanto, `EggSizeEnum` è completo come `Egg.EggSizeEnum` .</span><span class="sxs-lookup"><span data-stu-id="281b7-204">Therefore, `EggSizeEnum` is fully qualified as `Egg.EggSizeEnum`.</span></span>

[!code-vb[VbEnumsTask#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#42)]

## <a name="example"></a><span data-ttu-id="281b7-205">Esempio</span><span class="sxs-lookup"><span data-stu-id="281b7-205">Example</span></span>

<span data-ttu-id="281b7-206">Nell'esempio seguente viene utilizzata l' `Enum` istruzione per definire un set correlato di valori costanti denominati.</span><span class="sxs-lookup"><span data-stu-id="281b7-206">The following example uses the `Enum` statement to define a related set of named constant values.</span></span> <span data-ttu-id="281b7-207">In questo caso, i valori sono i colori che è possibile scegliere per progettare moduli di immissione dati per un database.</span><span class="sxs-lookup"><span data-stu-id="281b7-207">In this case, the values are colors you might choose to design data entry forms for a database.</span></span>

[!code-vb[VbEnumsTask#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#30)]

## <a name="example"></a><span data-ttu-id="281b7-208">Esempio</span><span class="sxs-lookup"><span data-stu-id="281b7-208">Example</span></span>

<span data-ttu-id="281b7-209">Nell'esempio seguente vengono illustrati i valori che includono numeri positivi e negativi.</span><span class="sxs-lookup"><span data-stu-id="281b7-209">The following example shows values that include both positive and negative numbers.</span></span>

[!code-vb[VbEnumsTask#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#31)]

## <a name="example"></a><span data-ttu-id="281b7-210">Esempio</span><span class="sxs-lookup"><span data-stu-id="281b7-210">Example</span></span>

<span data-ttu-id="281b7-211">Nell'esempio seguente `As` viene usata una clausola per specificare l'oggetto `datatype` di un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="281b7-211">In the following example, an `As` clause is used to specify the `datatype` of an enumeration.</span></span>

[!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]

## <a name="example"></a><span data-ttu-id="281b7-212">Esempio</span><span class="sxs-lookup"><span data-stu-id="281b7-212">Example</span></span>

<span data-ttu-id="281b7-213">Nell'esempio seguente viene illustrato come utilizzare un'enumerazione bit per bit.</span><span class="sxs-lookup"><span data-stu-id="281b7-213">The following example shows how to use a bitwise enumeration.</span></span> <span data-ttu-id="281b7-214">È possibile assegnare più valori a un'istanza di un'enumerazione bit per bit.</span><span class="sxs-lookup"><span data-stu-id="281b7-214">Multiple values can be assigned to an instance of a bitwise enumeration.</span></span> <span data-ttu-id="281b7-215">La `Enum` dichiarazione include l' <xref:System.FlagsAttribute> attributo, che indica che l'enumerazione può essere considerata come un set di flag.</span><span class="sxs-lookup"><span data-stu-id="281b7-215">The `Enum` declaration includes the <xref:System.FlagsAttribute> attribute, which indicates that the enumeration can be treated as a set of flags.</span></span>

[!code-vb[VbEnumsTask#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#61)]

## <a name="example"></a><span data-ttu-id="281b7-216">Esempio</span><span class="sxs-lookup"><span data-stu-id="281b7-216">Example</span></span>

<span data-ttu-id="281b7-217">Nell'esempio seguente viene iterata un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="281b7-217">The following example iterates through an enumeration.</span></span> <span data-ttu-id="281b7-218">Usa il <xref:System.Enum.GetNames%2A> metodo per recuperare una matrice di nomi di membri dall'enumerazione e <xref:System.Enum.GetValues%2A> per recuperare una matrice di valori dei membri.</span><span class="sxs-lookup"><span data-stu-id="281b7-218">It uses the <xref:System.Enum.GetNames%2A> method to retrieve an array of member names from the enumeration, and <xref:System.Enum.GetValues%2A> to retrieve an array of member values.</span></span>

[!code-vb[VbEnumsTask#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#51)]

## <a name="see-also"></a><span data-ttu-id="281b7-219">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="281b7-219">See also</span></span>

- <xref:System.Enum>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [<span data-ttu-id="281b7-220">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="281b7-220">Const Statement</span></span>](const-statement.md)
- [<span data-ttu-id="281b7-221">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="281b7-221">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="281b7-222">Conversioni implicite ed esplicite</span><span class="sxs-lookup"><span data-stu-id="281b7-222">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="281b7-223">CString</span><span class="sxs-lookup"><span data-stu-id="281b7-223">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="281b7-224">Costanti ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="281b7-224">Constants and Enumerations</span></span>](../constants-and-enumerations.md)
