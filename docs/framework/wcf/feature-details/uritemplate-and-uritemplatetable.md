---
title: UriTemplate e UriTemplateTable
ms.date: 03/30/2017
ms.assetid: 5cbbe03f-4a9e-4d44-9e02-c5773239cf52
ms.openlocfilehash: b0dc3b2b747bc08da239490db7db3ba77d1e7ed8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130247"
---
# <a name="uritemplate-and-uritemplatetable"></a><span data-ttu-id="c1b43-102">UriTemplate e UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="c1b43-102">UriTemplate and UriTemplateTable</span></span>
<span data-ttu-id="c1b43-103">Gli sviluppatori Web devono poter essere in grado di descrivere la forma e il layout degli URI a cui rispondono i loro servizi.</span><span class="sxs-lookup"><span data-stu-id="c1b43-103">Web developers require the ability to describe the shape and layout of the URIs that their services respond to.</span></span> <span data-ttu-id="c1b43-104">Windows Communication Foundation (WCF) aggiunto due nuove classi per consentire agli sviluppatori di controllare gli URI.</span><span class="sxs-lookup"><span data-stu-id="c1b43-104">Windows Communication Foundation (WCF) added two new classes to give developers control over their URIs.</span></span> <xref:System.UriTemplate> <span data-ttu-id="c1b43-105">e <xref:System.UriTemplateTable> costituiscono la base del motore di invio basato su URI in WCF.</span><span class="sxs-lookup"><span data-stu-id="c1b43-105">and <xref:System.UriTemplateTable> form the basis of the URI-based dispatch engine in WCF.</span></span> <span data-ttu-id="c1b43-106">Queste classi possono essere utilizzate anche nel meccanismo del mapping delle proprie, consentendo agli sviluppatori di sfruttare i vantaggi dei modelli e l'URI senza implementare un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="c1b43-106">These classes can also be used on their own, allowing developers to take advantage of templates and the URI mapping mechanism without implementing a WCF service.</span></span>  
  
## <a name="templates"></a><span data-ttu-id="c1b43-107">Modelli</span><span class="sxs-lookup"><span data-stu-id="c1b43-107">Templates</span></span>  
 <span data-ttu-id="c1b43-108">I modelli consentono di descrivere set di URI relativi.</span><span class="sxs-lookup"><span data-stu-id="c1b43-108">A template is a way to describe a set of relative URIs.</span></span> <span data-ttu-id="c1b43-109">Nella tabella seguente il set di modelli URI illustra come definire un sistema per il recupero di vari tipi di informazioni meteorologiche.</span><span class="sxs-lookup"><span data-stu-id="c1b43-109">The set of URI templates in the following table shows how a system that retrieves various types of weather information might be defined.</span></span>  
  
|<span data-ttu-id="c1b43-110">Dati</span><span class="sxs-lookup"><span data-stu-id="c1b43-110">Data</span></span>|<span data-ttu-id="c1b43-111">Modello</span><span class="sxs-lookup"><span data-stu-id="c1b43-111">Template</span></span>|  
|----------|--------------|  
|<span data-ttu-id="c1b43-112">Previsioni nazionali</span><span class="sxs-lookup"><span data-stu-id="c1b43-112">National Forecast</span></span>|<span data-ttu-id="c1b43-113">previsioni/nazionali</span><span class="sxs-lookup"><span data-stu-id="c1b43-113">weather/national</span></span>|  
|<span data-ttu-id="c1b43-114">Previsioni regionali</span><span class="sxs-lookup"><span data-stu-id="c1b43-114">State Forecast</span></span>|<span data-ttu-id="c1b43-115">previsioni/{regione}</span><span class="sxs-lookup"><span data-stu-id="c1b43-115">weather/{state}</span></span>|  
|<span data-ttu-id="c1b43-116">Previsioni urbane</span><span class="sxs-lookup"><span data-stu-id="c1b43-116">City Forecast</span></span>|<span data-ttu-id="c1b43-117">previsioni/{regione}/{città}</span><span class="sxs-lookup"><span data-stu-id="c1b43-117">weather/{state}/{city}</span></span>|  
|<span data-ttu-id="c1b43-118">Previsioni di attività</span><span class="sxs-lookup"><span data-stu-id="c1b43-118">Activity Forecast</span></span>|<span data-ttu-id="c1b43-119">previsioni/{regione}/{città}/{attività}</span><span class="sxs-lookup"><span data-stu-id="c1b43-119">weather/{state}/{city}/{activity}</span></span>|  
  
 <span data-ttu-id="c1b43-120">Questa tabella descrive un insieme di URI simili fra loro dal punto di vista strutturale.</span><span class="sxs-lookup"><span data-stu-id="c1b43-120">This table describes a set of structurally similar URIs.</span></span> <span data-ttu-id="c1b43-121">Ogni voce è un modello URI.</span><span class="sxs-lookup"><span data-stu-id="c1b43-121">Each entry is a URI template.</span></span> <span data-ttu-id="c1b43-122">I segmenti nelle parentesi graffe descrivono variabili,</span><span class="sxs-lookup"><span data-stu-id="c1b43-122">The segments in curly braces describe variables.</span></span> <span data-ttu-id="c1b43-123">mentre quelli non all'interno di parentesi graffe descrivono stringhe letterali.</span><span class="sxs-lookup"><span data-stu-id="c1b43-123">The segments not in curly braces describe literal strings.</span></span> <span data-ttu-id="c1b43-124">Le classi di modello WCF consentono agli sviluppatori di sfruttare un URI in ingresso, ad esempio, "/ meteo/wa/seattle/ed esegue il ciclo" e confrontarla a un modello che descrive, "{regione} / previsioni / {città} / {attività}".</span><span class="sxs-lookup"><span data-stu-id="c1b43-124">The WCF template classes allow a developer to take an incoming URI, for example, "/weather/wa/seattle/cycling", and match it to a template that describes it, "/weather/{state}/{city}/{activity}".</span></span>  
  
## <a name="uritemplate"></a><span data-ttu-id="c1b43-125">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="c1b43-125">UriTemplate</span></span>  
 <xref:System.UriTemplate> <span data-ttu-id="c1b43-126">è una classe che incapsula un modello URI.</span><span class="sxs-lookup"><span data-stu-id="c1b43-126">is a class that encapsulates a URI template.</span></span> <span data-ttu-id="c1b43-127">Il costruttore accetta un parametro di stringa che definisce il modello.</span><span class="sxs-lookup"><span data-stu-id="c1b43-127">The constructor takes a string parameter that defines the template.</span></span> <span data-ttu-id="c1b43-128">Questa stringa contiene il modello nel formato descritto nella sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="c1b43-128">This string contains the template in the format described in the next section.</span></span> <span data-ttu-id="c1b43-129">La classe <xref:System.UriTemplate> fornisce metodi che consentono di mettere in corrispondenza un URI in ingresso con un modello, generare un URI a partire da un modello, recuperare una raccolta di nomi variabili utilizzati nel modello, determinare se due modelli sono equivalenti e restituire la stringa del modello.</span><span class="sxs-lookup"><span data-stu-id="c1b43-129">The <xref:System.UriTemplate> class provides methods that allow you match an incoming URI to a template, generate a URI from a template, retrieve a collection of variable names used in the template, determine whether two templates are equivalent, and return the template's string.</span></span>  
  
 <xref:System.UriTemplate.Match%28System.Uri%2CSystem.Uri%29> <span data-ttu-id="c1b43-130">accetta un indirizzo di base e un candidato URI e tenta di abbinare l'URI per il modello.</span><span class="sxs-lookup"><span data-stu-id="c1b43-130">takes a base address and a candidate URI and attempts to match the URI to the template.</span></span> <span data-ttu-id="c1b43-131">Se il tentativo ha esito positivo, viene restituita un'istanza della classe <xref:System.UriTemplateMatch>.</span><span class="sxs-lookup"><span data-stu-id="c1b43-131">If the match is successful, a <xref:System.UriTemplateMatch> instance is returned.</span></span> <span data-ttu-id="c1b43-132">L'oggetto <xref:System.UriTemplateMatch> contiene un URI di base, l'URI candidato, una raccolta nome/valore dei parametri di query, una matrice di segmenti di percorso relativo, una raccolta nome/valore di variabili di cui era stata creata una corrispondenza, l'istanza <xref:System.UriTemplate> utilizzata per creare la corrispondenza, una stringa contenente eventuali porzioni prive di corrispondenza dell'URI candidato (utilizzate se il modello contiene un carattere jolly) e un oggetto associato al modello.</span><span class="sxs-lookup"><span data-stu-id="c1b43-132">The <xref:System.UriTemplateMatch> object contains a base URI, the candidate URI, a name/value collection of the query parameters, an array of the relative path segments, a name/value collection of variables that were matched, the <xref:System.UriTemplate> instance used to perform the match, a string that contains any unmatched portion of the candidate URI (used when the template has a wildcard), and an object that is associated with the template.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1b43-133">Quando viene creata una corrispondenza tra un URI candidato e un modello, la classe <xref:System.UriTemplate> ignora lo schema e il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="c1b43-133">The <xref:System.UriTemplate> class ignores the scheme and port number when matching a candidate URI to a template.</span></span>  
  
 <span data-ttu-id="c1b43-134">Sono disponibili due metodi che consentono di generare un URI da un modello: <xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> e <xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29>.</span><span class="sxs-lookup"><span data-stu-id="c1b43-134">There are two methods that allow you to generate a URI from a template, <xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> and <xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29>.</span></span> <xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> <span data-ttu-id="c1b43-135">accetta un indirizzo di base e una raccolta nome/valore dei parametri.</span><span class="sxs-lookup"><span data-stu-id="c1b43-135">takes a base address and a name/value collection of parameters.</span></span> <span data-ttu-id="c1b43-136">Questi parametri vengono sostituiti con le variabili quando il modello viene associato.</span><span class="sxs-lookup"><span data-stu-id="c1b43-136">These parameters are substituted for variables when the template is bound.</span></span> <xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29> <span data-ttu-id="c1b43-137">accetta le coppie nome/valore e le sostituisce da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="c1b43-137">takes the name/value pairs and substitutes them left to right.</span></span>  
  
 <xref:System.UriTemplate.ToString> <span data-ttu-id="c1b43-138">Restituisce la stringa di modello.</span><span class="sxs-lookup"><span data-stu-id="c1b43-138">returns the template string.</span></span>  
  
 <span data-ttu-id="c1b43-139">La proprietà <xref:System.UriTemplate.PathSegmentVariableNames%2A> contiene la raccolta dei nomi delle variabili utilizzate all'interno dei segmenti di percorso contenuti nella stringa di modello.</span><span class="sxs-lookup"><span data-stu-id="c1b43-139">The <xref:System.UriTemplate.PathSegmentVariableNames%2A> property contains a collection of the names of the variables used within path segments in the template string.</span></span>  
  
 <xref:System.UriTemplate.IsEquivalentTo%28System.UriTemplate%29> <span data-ttu-id="c1b43-140">accetta un <xref:System.UriTemplate> come parametro e restituisce un valore booleano che specifica se i due modelli sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="c1b43-140">takes a <xref:System.UriTemplate> as a parameter and returns a Boolean value that specifies whether the two templates are equivalent.</span></span> <span data-ttu-id="c1b43-141">Per altre informazioni, vedere la sezione equivalenza fra modelli più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c1b43-141">For more information, see the Template Equivalence section later in this topic.</span></span>  
  
 <xref:System.UriTemplate> <span data-ttu-id="c1b43-142">è progettato per funzionare con qualsiasi schema URI conforme alla grammatica URI HTTP.</span><span class="sxs-lookup"><span data-stu-id="c1b43-142">is designed to work with any URI scheme that conforms to the HTTP URI grammar.</span></span> <span data-ttu-id="c1b43-143">Di seguito vengono riportati esempi di schemi URI supportati.</span><span class="sxs-lookup"><span data-stu-id="c1b43-143">The following are examples of supported URI schemes.</span></span>  
  
- <span data-ttu-id="c1b43-144">http://</span><span class="sxs-lookup"><span data-stu-id="c1b43-144">http://</span></span>  
  
- <span data-ttu-id="c1b43-145">https://</span><span class="sxs-lookup"><span data-stu-id="c1b43-145">https://</span></span>  
  
- <span data-ttu-id="c1b43-146">net.tcp://</span><span class="sxs-lookup"><span data-stu-id="c1b43-146">net.tcp://</span></span>  
  
- <span data-ttu-id="c1b43-147">net.pipe://</span><span class="sxs-lookup"><span data-stu-id="c1b43-147">net.pipe://</span></span>  
  
- <span data-ttu-id="c1b43-148">sb://</span><span class="sxs-lookup"><span data-stu-id="c1b43-148">sb://</span></span>  
  
 <span data-ttu-id="c1b43-149">Schemi come file:// e urn:// non sono conformi alla grammatica URI HTTP e causeranno risultati imprevisti se utilizzati con modelli URI.</span><span class="sxs-lookup"><span data-stu-id="c1b43-149">Schemes like file:// and urn:// do not conform to the HTTP URI grammar and cause unpredictable results when used with URI templates.</span></span>  
  
### <a name="template-string-syntax"></a><span data-ttu-id="c1b43-150">Sintassi della stringa di modello</span><span class="sxs-lookup"><span data-stu-id="c1b43-150">Template String Syntax</span></span>  
 <span data-ttu-id="c1b43-151">Ogni modello presenta tre parti: un percorso, una query facoltativa e un frammento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c1b43-151">A template has three parts: a path, an optional query, and an optional fragment.</span></span> <span data-ttu-id="c1b43-152">Si consideri ad esempio il modello seguente:</span><span class="sxs-lookup"><span data-stu-id="c1b43-152">For an example, see the following template:</span></span>  
  
```  
"/weather/{state}/{city}?forecast={length)#frag1  
```  
  
 <span data-ttu-id="c1b43-153">Il percorso è "/previsioni/{regione}/{città}", la query è "?previsioni={durata)" e il frammento è "#framm1".</span><span class="sxs-lookup"><span data-stu-id="c1b43-153">The path consists of "/weather/{state}/{city}", the query consists of "?forecast={length}, and the fragment consists of "#frag1".</span></span>  
  
 <span data-ttu-id="c1b43-154">Le barre iniziali e finali sono facoltative nell'espressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="c1b43-154">Leading and trailing slashes are optional in the path expression.</span></span> <span data-ttu-id="c1b43-155">Le espressioni di query e di frammento possono essere omesse del tutto.</span><span class="sxs-lookup"><span data-stu-id="c1b43-155">Both the query and fragment expressions can be omitted entirely.</span></span> <span data-ttu-id="c1b43-156">Un percorso è costituito da una serie di segmenti delimitati dal simbolo '/', ogni segmento può avere un valore letterale, un nome di variabile (scritto in parentesi le parentesi graffe {}) o un carattere jolly (scritto come\*').</span><span class="sxs-lookup"><span data-stu-id="c1b43-156">A path consists of a series of segments delimited by '/', each segment can have a literal value, a variable name (written in {curly braces}), or a wildcard (written as '\*').</span></span> <span data-ttu-id="c1b43-157">Nel modello precedente il segmento "\previsioni\ è un valore letterale, mentre"{regione}" e "{città}" rappresentano variabili.</span><span class="sxs-lookup"><span data-stu-id="c1b43-157">In the previous template the "\weather\ segment is a literal value while "{state}" and "{city}" are variables.</span></span> <span data-ttu-id="c1b43-158">Le variabili hanno il proprio nome dal contenuto delle parentesi graffe e in un secondo momento può essere sostituiti con un valore concreto per creare un *URI chiuso*.</span><span class="sxs-lookup"><span data-stu-id="c1b43-158">Variables take their name from the contents of their curly braces and they can later be replaced with a concrete value to create a *closed URI*.</span></span> <span data-ttu-id="c1b43-159">Il carattere jolly è facoltativo, ma può comparire solo alla fine dell'URI, in cui una corrispondenza logica con "il resto del percorso".</span><span class="sxs-lookup"><span data-stu-id="c1b43-159">The wildcard is optional, but can only appear at the end of the URI, where it logically matches "the rest of the path".</span></span>  
  
 <span data-ttu-id="c1b43-160">L'espressione di query, se presente, specifica una serie di coppie nome/valore non ordinate delimitate da '&'.</span><span class="sxs-lookup"><span data-stu-id="c1b43-160">The query expression, if present, specifies a series of unordered name/value pairs delimited by '&'.</span></span> <span data-ttu-id="c1b43-161">Gli elementi dell'espressione di query possono essere coppie letterali (x=2) o una coppia variabile (x={var}).</span><span class="sxs-lookup"><span data-stu-id="c1b43-161">Elements of the query expression can either be literal pairs (x=2) or a variable pair (x={var}).</span></span> <span data-ttu-id="c1b43-162">Solo il lato destro della query può contenere un'espressione variabile.</span><span class="sxs-lookup"><span data-stu-id="c1b43-162">Only the right side of the query can have a variable expression.</span></span> <span data-ttu-id="c1b43-163">({someName} = {someValue} non è consentito.</span><span class="sxs-lookup"><span data-stu-id="c1b43-163">({someName} = {someValue} is not allowed.</span></span> <span data-ttu-id="c1b43-164">Non è consentito utilizzare valori non abbinati (?x).</span><span class="sxs-lookup"><span data-stu-id="c1b43-164">Unpaired values (?x) are not permitted.</span></span> <span data-ttu-id="c1b43-165">Non c'è differenza tra un'espressione di query vuota e un'espressione di query contenente il solo carattere "?". Entrambe significano infatti "qualsiasi query".</span><span class="sxs-lookup"><span data-stu-id="c1b43-165">There is no difference between an empty query expression and a query expression consisting of just a single '?' (both mean "any query").</span></span>  
  
 <span data-ttu-id="c1b43-166">L'espressione di frammento può essere data da un valore letterale. Non sono consentite le variabili.</span><span class="sxs-lookup"><span data-stu-id="c1b43-166">The fragment expression can consist of a literal value, no variables are allowed.</span></span>  
  
 <span data-ttu-id="c1b43-167">Tutti i nomi variabili del modello contenuti in una stringa di modello devono essere univoci.</span><span class="sxs-lookup"><span data-stu-id="c1b43-167">All template variable names within a template string must be unique.</span></span> <span data-ttu-id="c1b43-168">I nomi variabili del modello non fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="c1b43-168">Template variable names are case-insensitive.</span></span>  
  
 <span data-ttu-id="c1b43-169">Esempi di stringhe di modello valide:</span><span class="sxs-lookup"><span data-stu-id="c1b43-169">Examples of valid template strings:</span></span>  
  
- <span data-ttu-id="c1b43-170">""</span><span class="sxs-lookup"><span data-stu-id="c1b43-170">""</span></span>  
  
- <span data-ttu-id="c1b43-171">"/casa"</span><span class="sxs-lookup"><span data-stu-id="c1b43-171">"/shoe"</span></span>  
  
- <span data-ttu-id="c1b43-172">"/shoe/\*"</span><span class="sxs-lookup"><span data-stu-id="c1b43-172">"/shoe/\*"</span></span>  
  
- <span data-ttu-id="c1b43-173">"{casa}/stanza"</span><span class="sxs-lookup"><span data-stu-id="c1b43-173">"{shoe}/boat"</span></span>  
  
- <span data-ttu-id="c1b43-174">"{casa} / {barca} /bed/ {quilt}"</span><span class="sxs-lookup"><span data-stu-id="c1b43-174">"{shoe}/{boat}/bed/{quilt}"</span></span>  
  
- <span data-ttu-id="c1b43-175">"casa / {barca}"</span><span class="sxs-lookup"><span data-stu-id="c1b43-175">"shoe/{boat}"</span></span>  
  
- <span data-ttu-id="c1b43-176">"casa / {barca} /\*"</span><span class="sxs-lookup"><span data-stu-id="c1b43-176">"shoe/{boat}/\*"</span></span>  
  
- <span data-ttu-id="c1b43-177">"casa/barca? x = 2"</span><span class="sxs-lookup"><span data-stu-id="c1b43-177">"shoe/boat?x=2"</span></span>  
  
- <span data-ttu-id="c1b43-178">"casa / {barca}? x = {bed}"</span><span class="sxs-lookup"><span data-stu-id="c1b43-178">"shoe/{boat}?x={bed}"</span></span>  
  
- <span data-ttu-id="c1b43-179">"casa / {barca}? x = {bed} & y = fuori banda"</span><span class="sxs-lookup"><span data-stu-id="c1b43-179">"shoe/{boat}?x={bed}&y=band"</span></span>  
  
- <span data-ttu-id="c1b43-180">"?x={shoe}"</span><span class="sxs-lookup"><span data-stu-id="c1b43-180">"?x={shoe}"</span></span>  
  
- <span data-ttu-id="c1b43-181">"shoe?x=3&y={var}</span><span class="sxs-lookup"><span data-stu-id="c1b43-181">"shoe?x=3&y={var}</span></span>  
  
 <span data-ttu-id="c1b43-182">Esempi di stringhe di modello non valide:</span><span class="sxs-lookup"><span data-stu-id="c1b43-182">Examples of invalid template strings:</span></span>  
  
- <span data-ttu-id="c1b43-183">"{casa} / {casa} / x = 2": nomi variabili duplicati.</span><span class="sxs-lookup"><span data-stu-id="c1b43-183">"{shoe}/{SHOE}/x=2" – Duplicate variable names.</span></span>  
  
- <span data-ttu-id="c1b43-184">"{casa} /stanza/? letto = {casa}": nomi variabili duplicati.</span><span class="sxs-lookup"><span data-stu-id="c1b43-184">"{shoe}/boat/?bed={shoe}" – Duplicate variable names.</span></span>  
  
- <span data-ttu-id="c1b43-185">"? x = x & amp;2 = 3" – coppie nome/valore all'interno di una stringa di query devono essere univoche, anche se sono valori letterali.</span><span class="sxs-lookup"><span data-stu-id="c1b43-185">"?x=2&x=3" – Name/value pairs within a query string must be unique, even if they are literals.</span></span>  
  
- <span data-ttu-id="c1b43-186">"? x = 2 &", stringa di Query non è valida.</span><span class="sxs-lookup"><span data-stu-id="c1b43-186">"?x=2&" – Query string is malformed.</span></span>  
  
- <span data-ttu-id="c1b43-187">"? 2 2&x = {casa}"-stringa di Query deve contenere coppie nome/valore.</span><span class="sxs-lookup"><span data-stu-id="c1b43-187">"?2&x={shoe}" – Query string must be name/value pairs.</span></span>  
  
- <span data-ttu-id="c1b43-188">"? y = 2 & & X = 3", stringa di Query deve contenere coppie nome / valore, i nomi non possono iniziare con '&'.</span><span class="sxs-lookup"><span data-stu-id="c1b43-188">"?y=2&&X=3" – Query string must be name value pairs, names cannot start with '&'.</span></span>  
  
### <a name="compound-path-segments"></a><span data-ttu-id="c1b43-189">Segmenti di percorso composti</span><span class="sxs-lookup"><span data-stu-id="c1b43-189">Compound Path Segments</span></span>  
 <span data-ttu-id="c1b43-190">I segmenti di percorso composti consentono a un singolo segmento di percorso URI di contenere più variabili, nonché variabili combinate con valori letterali.</span><span class="sxs-lookup"><span data-stu-id="c1b43-190">Compound path segments allow a single URI path segment to contain multiple variables as well as variables combined with literals.</span></span> <span data-ttu-id="c1b43-191">Di seguito vengono riportati esempi di segmenti di percorso composti validi.</span><span class="sxs-lookup"><span data-stu-id="c1b43-191">The following are examples of valid compound path segments.</span></span>  
  
- <span data-ttu-id="c1b43-192">/nomefile.{ext}/</span><span class="sxs-lookup"><span data-stu-id="c1b43-192">/filename.{ext}/</span></span>  
  
- <span data-ttu-id="c1b43-193">/{nomefile}.jpg/</span><span class="sxs-lookup"><span data-stu-id="c1b43-193">/{filename}.jpg/</span></span>  
  
- <span data-ttu-id="c1b43-194">/{nomefile}.{ext}/</span><span class="sxs-lookup"><span data-stu-id="c1b43-194">/{filename}.{ext}/</span></span>  
  
- <span data-ttu-id="c1b43-195">/{a}.{b}someLiteral{c}({d})/</span><span class="sxs-lookup"><span data-stu-id="c1b43-195">/{a}.{b}someLiteral{c}({d})/</span></span>  
  
 <span data-ttu-id="c1b43-196">Di seguito vengono riportati esempi di segmenti di percorso non validi.</span><span class="sxs-lookup"><span data-stu-id="c1b43-196">The following are examples of invalid path segments.</span></span>  
  
- <span data-ttu-id="c1b43-197">/{} -Variabili devono essere denominate.</span><span class="sxs-lookup"><span data-stu-id="c1b43-197">/{} - Variables must be named.</span></span>  
  
- <span data-ttu-id="c1b43-198">/{casa}{stanza}: le variabili devono essere separate da un valore letterale.</span><span class="sxs-lookup"><span data-stu-id="c1b43-198">/{shoe}{boat} - Variables must be separated by a literal.</span></span>  
  
### <a name="matching-and-compound-path-segments"></a><span data-ttu-id="c1b43-199">Segmenti di percorso composti e corrispondenti</span><span class="sxs-lookup"><span data-stu-id="c1b43-199">Matching and Compound Path Segments</span></span>  
 <span data-ttu-id="c1b43-200">I segmenti di percorso composti consentono di definire un UriTemplate che dispone di più variabili all'interno di un solo segmento di percorso.</span><span class="sxs-lookup"><span data-stu-id="c1b43-200">Compound path segments allow you to define a UriTemplate that has multiple variables within a single path segment.</span></span> <span data-ttu-id="c1b43-201">Ad esempio, nella stringa di modello seguente: "Punta / {state}. {Città} "due variabili (stato e città) sono definite all'interno del segmento stesso.</span><span class="sxs-lookup"><span data-stu-id="c1b43-201">For example, in the following template string: "Addresses/{state}.{city}" two variables (state and city) are defined within the same segment.</span></span> <span data-ttu-id="c1b43-202">Questo modello corrisponderebbe a un URL, ad esempio `http://example.com/Washington.Redmond` ma corrisponderà anche un URL come `http://example.com/Washington.Redmond.Microsoft`.</span><span class="sxs-lookup"><span data-stu-id="c1b43-202">This template would match a URL such as `http://example.com/Washington.Redmond` but it will also match an URL like `http://example.com/Washington.Redmond.Microsoft`.</span></span> <span data-ttu-id="c1b43-203">Nel secondo caso, la variabile di stato conterrà "Washington" e la variabile della città conterrà "Redmond".</span><span class="sxs-lookup"><span data-stu-id="c1b43-203">In the latter case, the state variable will contain "Washington" and the city variable will contain "Redmond.Microsoft".</span></span> <span data-ttu-id="c1b43-204">In questo caso il qualsiasi testo (eccetto '/') corrisponderà alla variabile {city}.</span><span class="sxs-lookup"><span data-stu-id="c1b43-204">In this case any text (except ‘/’) will match the {city} variable.</span></span> <span data-ttu-id="c1b43-205">Se si desidera un modello che non corrisponderà al testo "extra", posizionare la variabile in un segmento di modello separato, ad esempio: "Punta / {state} / {città}.</span><span class="sxs-lookup"><span data-stu-id="c1b43-205">If you want a template that will not match the "extra" text, place the variable in a separate template segment, for example: "Addresses/{state}/{city}.</span></span>  
  
### <a name="named-wildcard-segments"></a><span data-ttu-id="c1b43-206">Segmenti con caratteri jolly con nome</span><span class="sxs-lookup"><span data-stu-id="c1b43-206">Named Wildcard Segments</span></span>  
 <span data-ttu-id="c1b43-207">Un segmento con carattere jolly denominata è qualsiasi segmento variabile di percorso il cui nome di variabile inizia con il carattere jolly '\*'.</span><span class="sxs-lookup"><span data-stu-id="c1b43-207">A named wildcard segment is any path variable segment whose variable name begins with the wildcard character ‘\*’.</span></span> <span data-ttu-id="c1b43-208">La stringa di modello seguente contiene un segmento con carattere jolly con nome denominato "casa".</span><span class="sxs-lookup"><span data-stu-id="c1b43-208">The following template string contains a named wildcard segment named "shoe".</span></span>  
  
```  
"literal/{*shoe}"  
```  
  
 <span data-ttu-id="c1b43-209">I segmenti con caratteri jolly devono rispettare le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="c1b43-209">Wildcard segments must follow the following rules:</span></span>  
  
- <span data-ttu-id="c1b43-210">Per ogni stringa di modello può esistere al massimo un segmento con carattere jolly con nome.</span><span class="sxs-lookup"><span data-stu-id="c1b43-210">There can be at most one named wildcard segment for each template string.</span></span>  
  
- <span data-ttu-id="c1b43-211">Un segmento con carattere jolly con nome deve comparire nel segmento all'estrema destra del percorso.</span><span class="sxs-lookup"><span data-stu-id="c1b43-211">A named wildcard segment must appear at the right-most segment in the path.</span></span>  
  
- <span data-ttu-id="c1b43-212">Un segmento con carattere jolly con nome non può coesistere con un segmento con carattere jolly anonimo all'interno della stessa stringa di modello.</span><span class="sxs-lookup"><span data-stu-id="c1b43-212">A named wildcard segment cannot coexist with an anonymous wildcard segment within the same template string.</span></span>  
  
- <span data-ttu-id="c1b43-213">Il nome di un segmento con carattere jolly con nome deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="c1b43-213">The name of a named wildcard segment must be unique.</span></span>  
  
- <span data-ttu-id="c1b43-214">I segmenti con carattere jolly con nome non possono disporre di valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="c1b43-214">Named wildcard segments cannot have default values.</span></span>  
  
- <span data-ttu-id="c1b43-215">Segmenti con caratteri jolly denominato non possono terminare con "/".</span><span class="sxs-lookup"><span data-stu-id="c1b43-215">Named wildcard segments cannot end with "/".</span></span>  
  
### <a name="default-variable-values"></a><span data-ttu-id="c1b43-216">Valori di variabili predefiniti</span><span class="sxs-lookup"><span data-stu-id="c1b43-216">Default Variable Values</span></span>  
 <span data-ttu-id="c1b43-217">I valori di variabili predefiniti consentono di specificare valori predefiniti per variabili all'interno di un modello.</span><span class="sxs-lookup"><span data-stu-id="c1b43-217">Default variable values allow you to specify default values for variables within a template.</span></span> <span data-ttu-id="c1b43-218">È possibile specificare le variabili predefinite con parentesi graffe che dichiarano la variabile o come una raccolta passata al costruttore UriTemplate.</span><span class="sxs-lookup"><span data-stu-id="c1b43-218">Default variables can be specified with the curly braces that declare the variable or as a collection passed to the UriTemplate constructor.</span></span> <span data-ttu-id="c1b43-219">Nel modello seguente vengono illustrati due modi per specificare <xref:System.UriTemplate> con variabili con valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="c1b43-219">The following template shows two ways to specify a <xref:System.UriTemplate> with variables with default values.</span></span>  
  
```csharp
UriTemplate t = new UriTemplate("/test/{a=1}/{b=5}");  
```  
  
 <span data-ttu-id="c1b43-220">Questo modello dichiara una variabile denominata `a` con valore predefinito `1` e una variabile denominata `b` con valore predefinito `5`.</span><span class="sxs-lookup"><span data-stu-id="c1b43-220">This template declares a variable named `a` with a default value of `1` and a variable named `b` with a default value of `5`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1b43-221">Solo le variabili del segmento di percorso possono presentare valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="c1b43-221">Only path segment variables are allowed to have default values.</span></span> <span data-ttu-id="c1b43-222">Le variabili delle stringhe di query, dei segmenti composti e quelle con carattere jolly con nome non possono presentare valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="c1b43-222">Query string variables, compound segment variables, and named wildcard variables are not permitted to have default values.</span></span>  
  
 <span data-ttu-id="c1b43-223">Nell'esempio di codice seguente viene illustrato come gestire i valori di variabili predefiniti quando si crea una corrispondenza con un URI candidato.</span><span class="sxs-lookup"><span data-stu-id="c1b43-223">The following code shows how default variable values are handled when matching a candidate URI.</span></span>  
  
```csharp
Uri baseAddress = new Uri("http://localhost:8000/");

UriTemplate t = new UriTemplate("/{state=WA}/{city=Redmond}/", true);
Uri candidate = new Uri("http://localhost:8000/OR");

UriTemplateMatch m1 = t.Match(baseAddress, candidate);

Console.WriteLine($"Template: {t}");
Console.WriteLine($"Candidate URI: {candidate}");

// Display contents of BoundVariables
Console.WriteLine("BoundVariables:");
foreach (string key in m1.BoundVariables.AllKeys)
{
    Console.WriteLine($"\t{key}={m1.BoundVariables[key]}");
}
// The output of the above code is  
// Template: /{state=WA}/{city=Redmond}/
// Candidate URI: http://localhost:8000/OR
// BoundVariables:
//         STATE=OR
//         CITY=Redmond
```  
  
> [!NOTE]
> <span data-ttu-id="c1b43-224">Un URI, ad esempio `http://localhost:8000///` corrisponde al modello elencato nel codice precedente, tuttavia un URI, ad esempio `http://localhost:8000/` viene.</span><span class="sxs-lookup"><span data-stu-id="c1b43-224">A URI such as `http://localhost:8000///` does not match the template listed in the preceding code, however a URI such as `http://localhost:8000/` does.</span></span>  
  
 <span data-ttu-id="c1b43-225">Nell'esempio di codice seguente viene illustrato come gestire i valori di variabili predefiniti quando si crea un URI con un modello.</span><span class="sxs-lookup"><span data-stu-id="c1b43-225">The following code shows how default variable values are handled when creating a URI with a template.</span></span>  
  
```csharp
Uri baseAddress = new Uri("http://localhost:8000/");  
Dictionary<string,string> defVals = new Dictionary<string,string> {{"a","1"}, {"b", "5"}};  
UriTemplate t = new UriTemplate("/test/{a}/{b}", defVals);  
NameValueCollection vals = new NameValueCollection();  
vals.Add("a", "10");  
  
Uri boundUri = t.BindByName(baseAddress, vals);  
Console.WriteLine("BaseAddress: {0}", baseAddress);  
Console.WriteLine("Template: {0}", t.ToString());  
  
Console.WriteLine("Values: ");  
foreach (string key in vals.AllKeys)  
{  
    Console.WriteLine("\tKey = {0}, Value = {1}", key, vals[key]);  
}  
Console.WriteLine("Bound URI: {0}", boundUri);  
  
// The output of the preceding code is  
// BaseAddress: http://localhost:8000/  
// Template: /test/{a}/{b}  
// Values:  
//     Key = a, Value = 10  
// Bound URI: http://localhost:8000/test/10/5  
```  
  
<span data-ttu-id="c1b43-226">Quando a una variabile viene assegnato il valore predefinito `null`, è necessario tenere conto di alcuni vincoli aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="c1b43-226">When a variable is given a default value of `null` there are some additional constraints.</span></span> <span data-ttu-id="c1b43-227">Una variabile può presentare il valore predefinito `null` se è contenuta nel segmento più a destra della stringa del modello o se tutti i segmenti a destra del segmento presentano valori predefiniti `null`.</span><span class="sxs-lookup"><span data-stu-id="c1b43-227">A variable can have a default value of `null` if the variable is contained within the right most segment of the template string or if all segments to the right of the segment have default values of `null`.</span></span> <span data-ttu-id="c1b43-228">Di seguito vengono riportate stringhe di modello valide con valori predefiniti `null`:</span><span class="sxs-lookup"><span data-stu-id="c1b43-228">The following are valid template strings with default values of `null`:</span></span>  
  
- `UriTemplate t = new UriTemplate("shoe/{boat=null}");`

- `UriTemplate t = new UriTemplate("{shoe=null}/{boat=null}");`
  
- `UriTemplate t = new UriTemplate("{shoe=1}/{boat=null}");`

 <span data-ttu-id="c1b43-229">Di seguito vengono riportate stringhe di modello non valido con i valori predefiniti di `null`:</span><span class="sxs-lookup"><span data-stu-id="c1b43-229">The following are invalid template strings with default values of `null`:</span></span>  
  
- `UriTemplate t = new UriTemplate("{shoe=null}/boat"); // null default must be in the right most path segment`
  
- `UriTemplate t = new UriTemplate("{shoe=null}/{boat=x}/{bed=null}"); // shoe cannot have a null default because boat does not have a default null value`

### <a name="default-values-and-matching"></a><span data-ttu-id="c1b43-230">Valori predefiniti e corrispondenza</span><span class="sxs-lookup"><span data-stu-id="c1b43-230">Default Values and Matching</span></span>  
 <span data-ttu-id="c1b43-231">Quando si crea una corrispondenza tra un URI candidato e un modello con valori predefiniti, se i valori non sono specificati nell'URI candidato i valori predefiniti verranno inseriti nella raccolta <xref:System.UriTemplateMatch.BoundVariables%2A>.</span><span class="sxs-lookup"><span data-stu-id="c1b43-231">When matching a candidate URI with a template that has default values, the default values are placed in the <xref:System.UriTemplateMatch.BoundVariables%2A> collection if values are not specified in the candidate URI.</span></span>  
  
### <a name="template-equivalence"></a><span data-ttu-id="c1b43-232">Equivalenza fra modelli</span><span class="sxs-lookup"><span data-stu-id="c1b43-232">Template Equivalence</span></span>  
 <span data-ttu-id="c1b43-233">Due modelli si dice che trovano *strutturalmente equivalente* quando tutti i valori letterali dei modelli corrisponde e contengono variabili negli stessi segmenti.</span><span class="sxs-lookup"><span data-stu-id="c1b43-233">Two templates are said to be *structurally equivalent* when all of the templates' literals match and they have variables in the same segments.</span></span> <span data-ttu-id="c1b43-234">Ad esempio, i modelli seguenti sono strutturalmente equivalenti:</span><span class="sxs-lookup"><span data-stu-id="c1b43-234">For example the following templates are structurally equivalent:</span></span>  
  
- <span data-ttu-id="c1b43-235">/a/{var1}/b b/{var2}?x=1&y=2</span><span class="sxs-lookup"><span data-stu-id="c1b43-235">/a/{var1}/b b/{var2}?x=1&y=2</span></span>  
  
- <span data-ttu-id="c1b43-236">a/{x}/b%20b/{var1}?y=2&x=1</span><span class="sxs-lookup"><span data-stu-id="c1b43-236">a/{x}/b%20b/{var1}?y=2&x=1</span></span>  
  
- <span data-ttu-id="c1b43-237">a/{y}/B%20B/{z}/?y=2&x=1</span><span class="sxs-lookup"><span data-stu-id="c1b43-237">a/{y}/B%20B/{z}/?y=2&x=1</span></span>  
  
 <span data-ttu-id="c1b43-238">Alcune considerazioni:</span><span class="sxs-lookup"><span data-stu-id="c1b43-238">A few things to notice:</span></span>  
  
- <span data-ttu-id="c1b43-239">Se un modello contiene barre iniziali, solo la prima viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="c1b43-239">If a template contains leading slashes, only the first one is ignored.</span></span>  
  
- <span data-ttu-id="c1b43-240">Quando si verifica se due stringhe di modello sono strutturalmente equivalenti, i nomi variabili, i segmenti di percorso e le stringhe di query non fanno distinzione fra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="c1b43-240">When comparing template strings for structural equivalence, case is ignored for variable names and path segments, query strings are case sensitive.</span></span>  
  
- <span data-ttu-id="c1b43-241">Le stringhe di query non sono ordinate.</span><span class="sxs-lookup"><span data-stu-id="c1b43-241">Query strings are unordered.</span></span>  
  
## <a name="uritemplatetable"></a><span data-ttu-id="c1b43-242">UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="c1b43-242">UriTemplateTable</span></span>  
 <span data-ttu-id="c1b43-243">La classe <xref:System.UriTemplateTable> rappresenta una tabella associativa di oggetti <xref:System.UriTemplate> associata a un oggetto scelto dallo sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="c1b43-243">The <xref:System.UriTemplateTable> class represents an associative table of <xref:System.UriTemplate> objects bound to an object of the developer's choosing.</span></span> <span data-ttu-id="c1b43-244">Ogni tabella <xref:System.UriTemplateTable> deve contenere almeno un modello <xref:System.UriTemplate> prima di chiamare il metodo <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span><span class="sxs-lookup"><span data-stu-id="c1b43-244">A <xref:System.UriTemplateTable> must contain at least one <xref:System.UriTemplate> prior to calling <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span></span> <span data-ttu-id="c1b43-245">È possibile modificare il contenuto di <xref:System.UriTemplateTable> finché non viene chiamato il metodo <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span><span class="sxs-lookup"><span data-stu-id="c1b43-245">The contents of a <xref:System.UriTemplateTable> can be changed until <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called.</span></span> <span data-ttu-id="c1b43-246">Quando viene chiamato il metodo <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> viene eseguita una convalida</span><span class="sxs-lookup"><span data-stu-id="c1b43-246">Validation is performed when <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called.</span></span> <span data-ttu-id="c1b43-247">il cui tipo dipende dal valore del parametro `allowMultiple` da passare al metodo <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span><span class="sxs-lookup"><span data-stu-id="c1b43-247">The type of validation performed depends upon the value of the `allowMultiple` parameter to <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span></span>  
  
 <span data-ttu-id="c1b43-248">Quando al metodo <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> viene passato il valore `false`, l'oggetto <xref:System.UriTemplateTable> verifica se la tabella contiene modelli.</span><span class="sxs-lookup"><span data-stu-id="c1b43-248">When <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called passing in `false`, the <xref:System.UriTemplateTable> checks to make sure there are no templates in the table.</span></span> <span data-ttu-id="c1b43-249">Se rileva modelli strutturalmente equivalenti, genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c1b43-249">If it finds any structurally equivalent templates, it throws an exception.</span></span> <span data-ttu-id="c1b43-250">Questo metodo viene utilizzato insieme al metodo <xref:System.UriTemplateTable.MatchSingle%28System.Uri%29> quando si desidera garantire che solo un modello corrisponda a un determinato URI in ingresso.</span><span class="sxs-lookup"><span data-stu-id="c1b43-250">This is used in conjunction with <xref:System.UriTemplateTable.MatchSingle%28System.Uri%29> when you want to ensure only one template matches an incoming URI.</span></span>  
  
 <span data-ttu-id="c1b43-251">Quando viene chiamato il metodo <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> passando `true`, <xref:System.UriTemplateTable> consente la presenza di più modelli strutturalmente equivalenti all'interno di <xref:System.UriTemplateTable>.</span><span class="sxs-lookup"><span data-stu-id="c1b43-251">When <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called passing in `true`, <xref:System.UriTemplateTable> allows multiple, structurally-equivalent templates to be contained within a <xref:System.UriTemplateTable>.</span></span>  
  
 <span data-ttu-id="c1b43-252">Se un set di oggetti <xref:System.UriTemplate> aggiunti a un oggetto <xref:System.UriTemplateTable> contiene stringhe di query, queste non devono essere ambigue.</span><span class="sxs-lookup"><span data-stu-id="c1b43-252">If a set of <xref:System.UriTemplate> objects added to a <xref:System.UriTemplateTable> contain query strings they must not be ambiguous.</span></span> <span data-ttu-id="c1b43-253">È tuttavia consentito utilizzare stringhe di query identiche.</span><span class="sxs-lookup"><span data-stu-id="c1b43-253">Identical query strings are allowed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1b43-254">Mentre <xref:System.UriTemplateTable> consente la presenza di indirizzi di base che utilizzano schemi diversi da HTTP, lo schema e il numero di porta vengono ignorati quando si creano corrispondenze tra URI candidati e modelli.</span><span class="sxs-lookup"><span data-stu-id="c1b43-254">While the <xref:System.UriTemplateTable> allows base addresses that use schemes other than HTTP, the scheme and port number are ignored when matching candidate URIs to templates.</span></span>  
  
### <a name="query-string-ambiguity"></a><span data-ttu-id="c1b43-255">Ambiguità delle stringhe di query</span><span class="sxs-lookup"><span data-stu-id="c1b43-255">Query String Ambiguity</span></span>  
 <span data-ttu-id="c1b43-256">I modelli che condividono un percorso equivalente contengono stringhe di query ambigue se esiste un URI che corrisponde a più di un modello.</span><span class="sxs-lookup"><span data-stu-id="c1b43-256">Templates that share an equivalent path contain ambiguous query strings if there is a URI that matches more than one template.</span></span>  
  
 <span data-ttu-id="c1b43-257">I set seguenti di stringhe di query non sono ambigui fra loro:</span><span class="sxs-lookup"><span data-stu-id="c1b43-257">The following sets of query strings are unambiguous within themselves:</span></span>  
  
- <span data-ttu-id="c1b43-258">?x=1</span><span class="sxs-lookup"><span data-stu-id="c1b43-258">?x=1</span></span>  
  
- <span data-ttu-id="c1b43-259">?x=2</span><span class="sxs-lookup"><span data-stu-id="c1b43-259">?x=2</span></span>  
  
- <span data-ttu-id="c1b43-260">?x=3</span><span class="sxs-lookup"><span data-stu-id="c1b43-260">?x=3</span></span>  
  
- <span data-ttu-id="c1b43-261">?x=1&y={var}</span><span class="sxs-lookup"><span data-stu-id="c1b43-261">?x=1&y={var}</span></span>  
  
- <span data-ttu-id="c1b43-262">?x=2&z={var}</span><span class="sxs-lookup"><span data-stu-id="c1b43-262">?x=2&z={var}</span></span>  
  
- <span data-ttu-id="c1b43-263">?x=3</span><span class="sxs-lookup"><span data-stu-id="c1b43-263">?x=3</span></span>  
  
- <span data-ttu-id="c1b43-264">?x=1</span><span class="sxs-lookup"><span data-stu-id="c1b43-264">?x=1</span></span>  
  
- <span data-ttu-id="c1b43-265">?</span><span class="sxs-lookup"><span data-stu-id="c1b43-265">?</span></span>  
  
- <span data-ttu-id="c1b43-266">?</span><span class="sxs-lookup"><span data-stu-id="c1b43-266">?</span></span> <span data-ttu-id="c1b43-267">x={var}</span><span class="sxs-lookup"><span data-stu-id="c1b43-267">x={var}</span></span>  
  
- <span data-ttu-id="c1b43-268">?</span><span class="sxs-lookup"><span data-stu-id="c1b43-268">?</span></span>  
  
- <span data-ttu-id="c1b43-269">?m=get&c=rss</span><span class="sxs-lookup"><span data-stu-id="c1b43-269">?m=get&c=rss</span></span>  
  
- <span data-ttu-id="c1b43-270">?m=put&c=rss</span><span class="sxs-lookup"><span data-stu-id="c1b43-270">?m=put&c=rss</span></span>  
  
- <span data-ttu-id="c1b43-271">?m=get&c=atom</span><span class="sxs-lookup"><span data-stu-id="c1b43-271">?m=get&c=atom</span></span>  
  
- <span data-ttu-id="c1b43-272">?m=put&c=atom</span><span class="sxs-lookup"><span data-stu-id="c1b43-272">?m=put&c=atom</span></span>  
  
 <span data-ttu-id="c1b43-273">I set seguenti di modelli di stringhe di query sono ambigui fra loro:</span><span class="sxs-lookup"><span data-stu-id="c1b43-273">The following sets of query string templates are ambiguous within themselves:</span></span>  
  
- <span data-ttu-id="c1b43-274">?x=1</span><span class="sxs-lookup"><span data-stu-id="c1b43-274">?x=1</span></span>  
  
- <span data-ttu-id="c1b43-275">?x={var}</span><span class="sxs-lookup"><span data-stu-id="c1b43-275">?x={var}</span></span>  
  
 <span data-ttu-id="c1b43-276">"x=1": corrisponde a entrambi i modelli.</span><span class="sxs-lookup"><span data-stu-id="c1b43-276">"x=1" - Matches both templates.</span></span>  
  
- <span data-ttu-id="c1b43-277">?x=1</span><span class="sxs-lookup"><span data-stu-id="c1b43-277">?x=1</span></span>  
  
- <span data-ttu-id="c1b43-278">?y=2</span><span class="sxs-lookup"><span data-stu-id="c1b43-278">?y=2</span></span>  
  
 <span data-ttu-id="c1b43-279">"x = 1 & y = 2" corrisponde a entrambi i modelli.</span><span class="sxs-lookup"><span data-stu-id="c1b43-279">"x=1&y=2" matches both templates.</span></span> <span data-ttu-id="c1b43-280">Ciò è dovuto al fatto che una stringa di query può contenere più variabili di stringa rispetto al modello a cui corrisponde.</span><span class="sxs-lookup"><span data-stu-id="c1b43-280">This is because a query string may contain more query string variables then the template it matches.</span></span>  
  
- <span data-ttu-id="c1b43-281">?x=1</span><span class="sxs-lookup"><span data-stu-id="c1b43-281">?x=1</span></span>  
  
- <span data-ttu-id="c1b43-282">?x=1&y={var}</span><span class="sxs-lookup"><span data-stu-id="c1b43-282">?x=1&y={var}</span></span>  
  
 <span data-ttu-id="c1b43-283">"x = y & amp;1 = 3" corrisponde a entrambi i modelli.</span><span class="sxs-lookup"><span data-stu-id="c1b43-283">"x=1&y=3" matches both templates.</span></span>  
  
- <span data-ttu-id="c1b43-284">?x=3&y=4</span><span class="sxs-lookup"><span data-stu-id="c1b43-284">?x=3&y=4</span></span>  
  
- <span data-ttu-id="c1b43-285">?x=3&z=5</span><span class="sxs-lookup"><span data-stu-id="c1b43-285">?x=3&z=5</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c1b43-286">I caratteri á e Á sono considerati caratteri diversi quando vengono visualizzate come parte del percorso di un URI o <xref:System.UriTemplate> segmento del percorso letterale (ma i caratteri e sono considerati lo stesso).</span><span class="sxs-lookup"><span data-stu-id="c1b43-286">The characters á and Á are considered to be different characters when they appear as part of a URI path or <xref:System.UriTemplate> path segment literal (but the characters a and A are considered to be the same).</span></span> <span data-ttu-id="c1b43-287">I caratteri á e Á vengono considerati gli stessi caratteri quando vengono visualizzate come parte di un <xref:System.UriTemplate> {variableName} o stringa di query di oggetto (e a e sono inoltre considerati gli stessi caratteri).</span><span class="sxs-lookup"><span data-stu-id="c1b43-287">The characters á and Á are considered to be the same characters when they appear as part of a <xref:System.UriTemplate> {variableName} or a query string (and a and A are also considered to be the same characters).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1b43-288">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1b43-288">See also</span></span>

- [<span data-ttu-id="c1b43-289">Panoramica sul modello di programmazione HTTP Web WCF</span><span class="sxs-lookup"><span data-stu-id="c1b43-289">WCF Web HTTP Programming Model Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)
- [<span data-ttu-id="c1b43-290">Modello a oggetti per la programmazione HTTP Web di WCF</span><span class="sxs-lookup"><span data-stu-id="c1b43-290">WCF Web HTTP Programming Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md)
- [<span data-ttu-id="c1b43-291">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="c1b43-291">UriTemplate</span></span>](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
- [<span data-ttu-id="c1b43-292">Tabella UriTemplate</span><span class="sxs-lookup"><span data-stu-id="c1b43-292">UriTemplate Table</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)
- [<span data-ttu-id="c1b43-293">Dispatcher della tabella UriTemplate</span><span class="sxs-lookup"><span data-stu-id="c1b43-293">UriTemplate Table Dispatcher</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)
