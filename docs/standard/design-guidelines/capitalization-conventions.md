---
title: Convenzioni per l'utilizzo di maiuscole e minuscole
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
ms.openlocfilehash: 8af4a15e1e5b34c38b14c6b547cf44801bbf13e6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741767"
---
# <a name="capitalization-conventions"></a><span data-ttu-id="8417c-102">Convenzioni per l'utilizzo di maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="8417c-102">Capitalization Conventions</span></span>
<span data-ttu-id="8417c-103">Le linee guida in questo capitolo definiscono un metodo semplice per l'utilizzo di case che, quando vengono applicate in modo coerente, rendono facili da leggere gli identificatori di tipi, membri e parametri.</span><span class="sxs-lookup"><span data-stu-id="8417c-103">The guidelines in this chapter lay out a simple method for using case that, when applied consistently, make identifiers for types, members, and parameters easy to read.</span></span>

## <a name="capitalization-rules-for-identifiers"></a><span data-ttu-id="8417c-104">Regole relative alle maiuscole per gli identificatori</span><span class="sxs-lookup"><span data-stu-id="8417c-104">Capitalization Rules for Identifiers</span></span>
 <span data-ttu-id="8417c-105">Per distinguere le parole in un identificatore, sfruttare la prima lettera di ogni parola nell'identificatore.</span><span class="sxs-lookup"><span data-stu-id="8417c-105">To differentiate words in an identifier, capitalize the first letter of each word in the identifier.</span></span> <span data-ttu-id="8417c-106">Non usare caratteri di sottolineatura per distinguere le parole, o per tale importanza, in qualsiasi punto degli identificatori.</span><span class="sxs-lookup"><span data-stu-id="8417c-106">Do not use underscores to differentiate words, or for that matter, anywhere in identifiers.</span></span> <span data-ttu-id="8417c-107">Esistono due modi appropriati per capitalizzare gli identificatori, a seconda dell'utilizzo dell'identificatore:</span><span class="sxs-lookup"><span data-stu-id="8417c-107">There are two appropriate ways to capitalize identifiers, depending on the use of the identifier:</span></span>

- <span data-ttu-id="8417c-108">Sistema Pascal</span><span class="sxs-lookup"><span data-stu-id="8417c-108">PascalCasing</span></span>

- <span data-ttu-id="8417c-109">camelCasing</span><span class="sxs-lookup"><span data-stu-id="8417c-109">camelCasing</span></span>

 <span data-ttu-id="8417c-110">La convenzione sistema Pascal, usata per tutti gli identificatori eccetto i nomi di parametro, converte in maiuscolo il primo carattere di ogni parola (inclusi gli acronimi per due lettere di lunghezza), come illustrato negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8417c-110">The PascalCasing convention, used for all identifiers except parameter names, capitalizes the first character of each word (including acronyms over two letters in length), as shown in the following examples:</span></span>

 `PropertyDescriptor`
 `HtmlTag`

 <span data-ttu-id="8417c-111">Viene creato un caso speciale per gli acronimi di due lettere in cui entrambe le lettere sono in maiuscolo, come illustrato nell'identificatore seguente:</span><span class="sxs-lookup"><span data-stu-id="8417c-111">A special case is made for two-letter acronyms in which both letters are capitalized, as shown in the following identifier:</span></span>

 `IOStream`

 <span data-ttu-id="8417c-112">La convenzione camelCasing, usata solo per i nomi dei parametri, converte in maiuscolo il primo carattere di ogni parola eccetto la prima parola, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="8417c-112">The camelCasing convention, used only for parameter names, capitalizes the first character of each word except the first word, as shown in the following examples.</span></span> <span data-ttu-id="8417c-113">Come illustrato nell'esempio, gli acronimi a due lettere che iniziano un identificatore con distinzione tra maiuscole e minuscole sono entrambi minuscoli.</span><span class="sxs-lookup"><span data-stu-id="8417c-113">As the example also shows, two-letter acronyms that begin a camel-cased identifier are both lowercase.</span></span>

 `propertyDescriptor`
 `ioStream`
 `htmlTag`

 <span data-ttu-id="8417c-114">✔️ utilizzare sistema Pascal per tutti i nomi di membri, tipi e spazi dei nomi pubblici costituiti da più parole.</span><span class="sxs-lookup"><span data-stu-id="8417c-114">✔️ DO use PascalCasing for all public member, type, and namespace names consisting of multiple words.</span></span>

 <span data-ttu-id="8417c-115">✔️ utilizzare camelCasing per i nomi dei parametri.</span><span class="sxs-lookup"><span data-stu-id="8417c-115">✔️ DO use camelCasing for parameter names.</span></span>

 <span data-ttu-id="8417c-116">Nella tabella seguente vengono descritte le regole di utilizzo delle maiuscole per diversi tipi di identificatori.</span><span class="sxs-lookup"><span data-stu-id="8417c-116">The following table describes the capitalization rules for different types of identifiers.</span></span>

|<span data-ttu-id="8417c-117">Identificatore</span><span class="sxs-lookup"><span data-stu-id="8417c-117">Identifier</span></span>|<span data-ttu-id="8417c-118">Maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="8417c-118">Casing</span></span>|<span data-ttu-id="8417c-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="8417c-119">Example</span></span>|
|----------------|------------|-------------|
|<span data-ttu-id="8417c-120">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="8417c-120">Namespace</span></span>|<span data-ttu-id="8417c-121">Pascal</span><span class="sxs-lookup"><span data-stu-id="8417c-121">Pascal</span></span>|`namespace System.Security { ... }`|
|<span data-ttu-id="8417c-122">Tipo di</span><span class="sxs-lookup"><span data-stu-id="8417c-122">Type</span></span>|<span data-ttu-id="8417c-123">Pascal</span><span class="sxs-lookup"><span data-stu-id="8417c-123">Pascal</span></span>|`public class StreamReader { ... }`|
|<span data-ttu-id="8417c-124">Interfaccia</span><span class="sxs-lookup"><span data-stu-id="8417c-124">Interface</span></span>|<span data-ttu-id="8417c-125">Pascal</span><span class="sxs-lookup"><span data-stu-id="8417c-125">Pascal</span></span>|`public interface IEnumerable { ... }`|
|<span data-ttu-id="8417c-126">Metodo</span><span class="sxs-lookup"><span data-stu-id="8417c-126">Method</span></span>|<span data-ttu-id="8417c-127">Pascal</span><span class="sxs-lookup"><span data-stu-id="8417c-127">Pascal</span></span>|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|
|<span data-ttu-id="8417c-128">Gli</span><span class="sxs-lookup"><span data-stu-id="8417c-128">Property</span></span>|<span data-ttu-id="8417c-129">Pascal</span><span class="sxs-lookup"><span data-stu-id="8417c-129">Pascal</span></span>|`public class String {` <br />  `public int Length { get; }` <br /> `}`|
|<span data-ttu-id="8417c-130">Event</span><span class="sxs-lookup"><span data-stu-id="8417c-130">Event</span></span>|<span data-ttu-id="8417c-131">Pascal</span><span class="sxs-lookup"><span data-stu-id="8417c-131">Pascal</span></span>|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|
|<span data-ttu-id="8417c-132">Campo</span><span class="sxs-lookup"><span data-stu-id="8417c-132">Field</span></span>|<span data-ttu-id="8417c-133">Pascal</span><span class="sxs-lookup"><span data-stu-id="8417c-133">Pascal</span></span>|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|
|<span data-ttu-id="8417c-134">Valore enum</span><span class="sxs-lookup"><span data-stu-id="8417c-134">Enum value</span></span>|<span data-ttu-id="8417c-135">Pascal</span><span class="sxs-lookup"><span data-stu-id="8417c-135">Pascal</span></span>|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|
|<span data-ttu-id="8417c-136">Parametro</span><span class="sxs-lookup"><span data-stu-id="8417c-136">Parameter</span></span>|<span data-ttu-id="8417c-137">Convenzione Camel</span><span class="sxs-lookup"><span data-stu-id="8417c-137">Camel</span></span>|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|

## <a name="capitalizing-compound-words-and-common-terms"></a><span data-ttu-id="8417c-138">Capitalizzazione di parole composte e termini comuni</span><span class="sxs-lookup"><span data-stu-id="8417c-138">Capitalizing Compound Words and Common Terms</span></span>
 <span data-ttu-id="8417c-139">La maggior parte dei termini composti viene considerata come una singola parola per scopi di maiuscole.</span><span class="sxs-lookup"><span data-stu-id="8417c-139">Most compound terms are treated as single words for purposes of capitalization.</span></span>

 <span data-ttu-id="8417c-140">❌ non capitalizzare ogni parola in cosiddette parole composte in formato chiuso.</span><span class="sxs-lookup"><span data-stu-id="8417c-140">❌ DO NOT capitalize each word in so-called closed-form compound words.</span></span>

 <span data-ttu-id="8417c-141">Si tratta di parole composte scritte come una singola parola, ad esempio endpoint.</span><span class="sxs-lookup"><span data-stu-id="8417c-141">These are compound words written as a single word, such as endpoint.</span></span> <span data-ttu-id="8417c-142">Ai fini delle linee guida per l'utilizzo di maiuscole e minuscole, considerare una parola composta a forma chiusa come una singola parola.</span><span class="sxs-lookup"><span data-stu-id="8417c-142">For the purpose of casing guidelines, treat a closed-form compound word as a single word.</span></span> <span data-ttu-id="8417c-143">Usare un dizionario corrente per determinare se una parola composta viene scritta in formato chiuso.</span><span class="sxs-lookup"><span data-stu-id="8417c-143">Use a current dictionary to determine if a compound word is written in closed form.</span></span>

|<span data-ttu-id="8417c-144">Pascal</span><span class="sxs-lookup"><span data-stu-id="8417c-144">Pascal</span></span>|<span data-ttu-id="8417c-145">Convenzione Camel</span><span class="sxs-lookup"><span data-stu-id="8417c-145">Camel</span></span>|<span data-ttu-id="8417c-146">not</span><span class="sxs-lookup"><span data-stu-id="8417c-146">Not</span></span>|
|------------|-----------|---------|
|`BitFlag`|`bitFlag`|`Bitflag`|
|`Callback`|`callback`|`CallBack`|
|`Canceled`|`canceled`|`Cancelled`|
|`DoNot`|`doNot`|`Don't`|
|`Email`|`email`|`EMail`|
|`Endpoint`|`endpoint`|`EndPoint`|
|`FileName`|`fileName`|`Filename`|
|`Gridline`|`gridline`|`GridLine`|
|`Hashtable`|`hashtable`|`HashTable`|
|`Id`|`id`|`ID`|
|`Indexes`|`indexes`|`Indices`|
|`LogOff`|`logOff`|`LogOut`|
|`LogOn`|`logOn`|`LogIn`|
|`Metadata`|`metadata`|`MetaData, metaData`|
|`Multipanel`|`multipanel`|`MultiPanel`|
|`Multiview`|`multiview`|`MultiView`|
|`Namespace`|`namespace`|`NameSpace`|
|`Ok`|`ok`|`OK`|
|`Pi`|`pi`|`PI`|
|`Placeholder`|`placeholder`|`PlaceHolder`|
|`SignIn`|`signIn`|`SignOn`|
|`SignOut`|`signOut`|`SignOff`|
|`UserName`|`userName`|`Username`|
|`WhiteSpace`|`whiteSpace`|`Whitespace`|
|`Writable`|`writable`|`Writeable`|

## <a name="case-sensitivity"></a><span data-ttu-id="8417c-147">Distinzione fra maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="8417c-147">Case Sensitivity</span></span>
 <span data-ttu-id="8417c-148">Le lingue che possono essere eseguite su CLR non devono supportare la distinzione tra maiuscole e minuscole, sebbene alcune operazioni.</span><span class="sxs-lookup"><span data-stu-id="8417c-148">Languages that can run on the CLR are not required to support case-sensitivity, although some do.</span></span> <span data-ttu-id="8417c-149">Anche se il linguaggio lo supporta, altre lingue che potrebbero accedere al Framework non lo sono.</span><span class="sxs-lookup"><span data-stu-id="8417c-149">Even if your language supports it, other languages that might access your framework do not.</span></span> <span data-ttu-id="8417c-150">Le API che sono accessibili esternamente, pertanto, non possono basarsi solo su case per distinguere tra due nomi nello stesso contesto.</span><span class="sxs-lookup"><span data-stu-id="8417c-150">Any APIs that are externally accessible, therefore, cannot rely on case alone to distinguish between two names in the same context.</span></span>

 <span data-ttu-id="8417c-151">❌ non presupporre che tutti i linguaggi di programmazione fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="8417c-151">❌ DO NOT assume that all programming languages are case sensitive.</span></span> <span data-ttu-id="8417c-152">Ma non lo sono.</span><span class="sxs-lookup"><span data-stu-id="8417c-152">They are not.</span></span> <span data-ttu-id="8417c-153">I nomi non possono differire solo per caso.</span><span class="sxs-lookup"><span data-stu-id="8417c-153">Names cannot differ by case alone.</span></span>

 <span data-ttu-id="8417c-154">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="8417c-154">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="8417c-155">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="8417c-155">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="8417c-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8417c-156">See also</span></span>

- [<span data-ttu-id="8417c-157">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="8417c-157">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="8417c-158">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="8417c-158">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
