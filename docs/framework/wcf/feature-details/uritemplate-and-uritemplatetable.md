---
title: UriTemplate e UriTemplateTable
ms.date: 03/30/2017
ms.assetid: 5cbbe03f-4a9e-4d44-9e02-c5773239cf52
ms.openlocfilehash: 2742217cb082f5c0354510a7e66818bafd6f1393
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144695"
---
# <a name="uritemplate-and-uritemplatetable"></a><span data-ttu-id="a56e9-102">UriTemplate e UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="a56e9-102">UriTemplate and UriTemplateTable</span></span>
<span data-ttu-id="a56e9-103">Gli sviluppatori Web devono poter essere in grado di descrivere la forma e il layout degli URI a cui rispondono i loro servizi.</span><span class="sxs-lookup"><span data-stu-id="a56e9-103">Web developers require the ability to describe the shape and layout of the URIs that their services respond to.</span></span> <span data-ttu-id="a56e9-104">Windows Communication Foundation (WCF) ha aggiunto due nuove classi per consentire agli sviluppatori di controllare gli URI.</span><span class="sxs-lookup"><span data-stu-id="a56e9-104">Windows Communication Foundation (WCF) added two new classes to give developers control over their URIs.</span></span> <span data-ttu-id="a56e9-105"><xref:System.UriTemplate>e <xref:System.UriTemplateTable> costituiscono la base del motore di invio basato su URI in WCF.</span><span class="sxs-lookup"><span data-stu-id="a56e9-105"><xref:System.UriTemplate> and <xref:System.UriTemplateTable> form the basis of the URI-based dispatch engine in WCF.</span></span> <span data-ttu-id="a56e9-106">Queste classi possono inoltre essere utilizzate autonomamente, consentendo agli sviluppatori di sfruttare i vantaggi dei modelli e del meccanismo di mapping degli URI senza implementare un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="a56e9-106">These classes can also be used on their own, allowing developers to take advantage of templates and the URI mapping mechanism without implementing a WCF service.</span></span>  
  
## <a name="templates"></a><span data-ttu-id="a56e9-107">Modelli</span><span class="sxs-lookup"><span data-stu-id="a56e9-107">Templates</span></span>  
 <span data-ttu-id="a56e9-108">I modelli consentono di descrivere set di URI relativi.</span><span class="sxs-lookup"><span data-stu-id="a56e9-108">A template is a way to describe a set of relative URIs.</span></span> <span data-ttu-id="a56e9-109">Nella tabella seguente il set di modelli URI illustra come definire un sistema per il recupero di vari tipi di informazioni meteorologiche.</span><span class="sxs-lookup"><span data-stu-id="a56e9-109">The set of URI templates in the following table shows how a system that retrieves various types of weather information might be defined.</span></span>  
  
|<span data-ttu-id="a56e9-110">Data</span><span class="sxs-lookup"><span data-stu-id="a56e9-110">Data</span></span>|<span data-ttu-id="a56e9-111">Modello</span><span class="sxs-lookup"><span data-stu-id="a56e9-111">Template</span></span>|  
|----------|--------------|  
|<span data-ttu-id="a56e9-112">Previsioni nazionali</span><span class="sxs-lookup"><span data-stu-id="a56e9-112">National Forecast</span></span>|<span data-ttu-id="a56e9-113">previsioni/nazionali</span><span class="sxs-lookup"><span data-stu-id="a56e9-113">weather/national</span></span>|  
|<span data-ttu-id="a56e9-114">Previsioni regionali</span><span class="sxs-lookup"><span data-stu-id="a56e9-114">State Forecast</span></span>|<span data-ttu-id="a56e9-115">previsioni/{regione}</span><span class="sxs-lookup"><span data-stu-id="a56e9-115">weather/{state}</span></span>|  
|<span data-ttu-id="a56e9-116">Previsioni urbane</span><span class="sxs-lookup"><span data-stu-id="a56e9-116">City Forecast</span></span>|<span data-ttu-id="a56e9-117">previsioni/{regione}/{città}</span><span class="sxs-lookup"><span data-stu-id="a56e9-117">weather/{state}/{city}</span></span>|  
|<span data-ttu-id="a56e9-118">Previsioni di attività</span><span class="sxs-lookup"><span data-stu-id="a56e9-118">Activity Forecast</span></span>|<span data-ttu-id="a56e9-119">previsioni/{regione}/{città}/{attività}</span><span class="sxs-lookup"><span data-stu-id="a56e9-119">weather/{state}/{city}/{activity}</span></span>|  
  
 <span data-ttu-id="a56e9-120">Questa tabella descrive un insieme di URI simili fra loro dal punto di vista strutturale.</span><span class="sxs-lookup"><span data-stu-id="a56e9-120">This table describes a set of structurally similar URIs.</span></span> <span data-ttu-id="a56e9-121">Ogni voce è un modello URI.</span><span class="sxs-lookup"><span data-stu-id="a56e9-121">Each entry is a URI template.</span></span> <span data-ttu-id="a56e9-122">I segmenti nelle parentesi graffe descrivono variabili,</span><span class="sxs-lookup"><span data-stu-id="a56e9-122">The segments in curly braces describe variables.</span></span> <span data-ttu-id="a56e9-123">mentre quelli non all'interno di parentesi graffe descrivono stringhe letterali.</span><span class="sxs-lookup"><span data-stu-id="a56e9-123">The segments not in curly braces describe literal strings.</span></span> <span data-ttu-id="a56e9-124">Le classi modello WCF consentono a uno sviluppatore di accettare un URI in ingresso, ad esempio "/Weather/WA/Seattle/Cycling", e di associarlo a un modello che lo descrive, ovvero "/Weather/{state}/{City}/{Activity}".</span><span class="sxs-lookup"><span data-stu-id="a56e9-124">The WCF template classes allow a developer to take an incoming URI, for example, "/weather/wa/seattle/cycling", and match it to a template that describes it, "/weather/{state}/{city}/{activity}".</span></span>  
  
## <a name="uritemplate"></a><span data-ttu-id="a56e9-125">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="a56e9-125">UriTemplate</span></span>  
 <span data-ttu-id="a56e9-126">L'elemento <xref:System.UriTemplate> è una classe che incapsula un modello URI.</span><span class="sxs-lookup"><span data-stu-id="a56e9-126"><xref:System.UriTemplate> is a class that encapsulates a URI template.</span></span> <span data-ttu-id="a56e9-127">Il costruttore accetta un parametro di stringa che definisce il modello.</span><span class="sxs-lookup"><span data-stu-id="a56e9-127">The constructor takes a string parameter that defines the template.</span></span> <span data-ttu-id="a56e9-128">Questa stringa contiene il modello nel formato descritto nella sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="a56e9-128">This string contains the template in the format described in the next section.</span></span> <span data-ttu-id="a56e9-129">La classe <xref:System.UriTemplate> fornisce metodi che consentono di mettere in corrispondenza un URI in ingresso con un modello, generare un URI a partire da un modello, recuperare una raccolta di nomi variabili utilizzati nel modello, determinare se due modelli sono equivalenti e restituire la stringa del modello.</span><span class="sxs-lookup"><span data-stu-id="a56e9-129">The <xref:System.UriTemplate> class provides methods that allow you match an incoming URI to a template, generate a URI from a template, retrieve a collection of variable names used in the template, determine whether two templates are equivalent, and return the template's string.</span></span>  
  
 <span data-ttu-id="a56e9-130">Il metodo <xref:System.UriTemplate.Match%28System.Uri%2CSystem.Uri%29> accetta un indirizzo di base e un URI candidato e tenta di creare una corrispondenza tra l'URI e il modello.</span><span class="sxs-lookup"><span data-stu-id="a56e9-130"><xref:System.UriTemplate.Match%28System.Uri%2CSystem.Uri%29> takes a base address and a candidate URI and attempts to match the URI to the template.</span></span> <span data-ttu-id="a56e9-131">Se il tentativo ha esito positivo, viene restituita un'istanza della classe <xref:System.UriTemplateMatch>.</span><span class="sxs-lookup"><span data-stu-id="a56e9-131">If the match is successful, a <xref:System.UriTemplateMatch> instance is returned.</span></span> <span data-ttu-id="a56e9-132">L'oggetto <xref:System.UriTemplateMatch> contiene un URI di base, l'URI candidato, una raccolta nome/valore dei parametri di query, una matrice di segmenti di percorso relativo, una raccolta nome/valore di variabili di cui era stata creata una corrispondenza, l'istanza <xref:System.UriTemplate> utilizzata per creare la corrispondenza, una stringa contenente eventuali porzioni prive di corrispondenza dell'URI candidato (utilizzate se il modello contiene un carattere jolly) e un oggetto associato al modello.</span><span class="sxs-lookup"><span data-stu-id="a56e9-132">The <xref:System.UriTemplateMatch> object contains a base URI, the candidate URI, a name/value collection of the query parameters, an array of the relative path segments, a name/value collection of variables that were matched, the <xref:System.UriTemplate> instance used to perform the match, a string that contains any unmatched portion of the candidate URI (used when the template has a wildcard), and an object that is associated with the template.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a56e9-133">Quando viene creata una corrispondenza tra un URI candidato e un modello, la classe <xref:System.UriTemplate> ignora lo schema e il numero di porta.</span><span class="sxs-lookup"><span data-stu-id="a56e9-133">The <xref:System.UriTemplate> class ignores the scheme and port number when matching a candidate URI to a template.</span></span>  
  
 <span data-ttu-id="a56e9-134">Sono disponibili due metodi che consentono di generare un URI da un modello: <xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> e <xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29>.</span><span class="sxs-lookup"><span data-stu-id="a56e9-134">There are two methods that allow you to generate a URI from a template, <xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> and <xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29>.</span></span> <span data-ttu-id="a56e9-135">Il metodo <xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> accetta un indirizzo di base e una raccolta nome/valore di parametri.</span><span class="sxs-lookup"><span data-stu-id="a56e9-135"><xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> takes a base address and a name/value collection of parameters.</span></span> <span data-ttu-id="a56e9-136">Questi parametri vengono sostituiti con le variabili quando il modello viene associato.</span><span class="sxs-lookup"><span data-stu-id="a56e9-136">These parameters are substituted for variables when the template is bound.</span></span> <span data-ttu-id="a56e9-137">Il metodo <xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29> accetta invece le coppie nome/valore e le sostituisce da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="a56e9-137"><xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29> takes the name/value pairs and substitutes them left to right.</span></span>  
  
 <span data-ttu-id="a56e9-138">Il metodo <xref:System.UriTemplate.ToString> restituisce la stringa di modello.</span><span class="sxs-lookup"><span data-stu-id="a56e9-138"><xref:System.UriTemplate.ToString> returns the template string.</span></span>  
  
 <span data-ttu-id="a56e9-139">La proprietà <xref:System.UriTemplate.PathSegmentVariableNames%2A> contiene la raccolta dei nomi delle variabili utilizzate all'interno dei segmenti di percorso contenuti nella stringa di modello.</span><span class="sxs-lookup"><span data-stu-id="a56e9-139">The <xref:System.UriTemplate.PathSegmentVariableNames%2A> property contains a collection of the names of the variables used within path segments in the template string.</span></span>  
  
 <span data-ttu-id="a56e9-140">Il metodo <xref:System.UriTemplate.IsEquivalentTo%28System.UriTemplate%29> accetta un oggetto <xref:System.UriTemplate> come parametro e restituisce un valore booleano che specifica se i due modelli sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="a56e9-140"><xref:System.UriTemplate.IsEquivalentTo%28System.UriTemplate%29> takes a <xref:System.UriTemplate> as a parameter and returns a Boolean value that specifies whether the two templates are equivalent.</span></span> <span data-ttu-id="a56e9-141">Per ulteriori informazioni, vedere la sezione relativa all'equivalenza dei modelli più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a56e9-141">For more information, see the Template Equivalence section later in this topic.</span></span>  
  
 <span data-ttu-id="a56e9-142"><xref:System.UriTemplate> può essere utilizzato con qualsiasi schema URI conforme alla grammatica URI HTTP.</span><span class="sxs-lookup"><span data-stu-id="a56e9-142"><xref:System.UriTemplate> is designed to work with any URI scheme that conforms to the HTTP URI grammar.</span></span> <span data-ttu-id="a56e9-143">Di seguito vengono riportati esempi di schemi URI supportati.</span><span class="sxs-lookup"><span data-stu-id="a56e9-143">The following are examples of supported URI schemes.</span></span>  
  
- `http://`  
  
- `https://`  
  
- `net.tcp://`  
  
- `net.pipe://`  
  
- `sb://`  
  
 <span data-ttu-id="a56e9-144">Schemi come file:// e urn:// non sono conformi alla grammatica URI HTTP e causeranno risultati imprevisti se utilizzati con modelli URI.</span><span class="sxs-lookup"><span data-stu-id="a56e9-144">Schemes like file:// and urn:// do not conform to the HTTP URI grammar and cause unpredictable results when used with URI templates.</span></span>  
  
### <a name="template-string-syntax"></a><span data-ttu-id="a56e9-145">Sintassi della stringa di modello</span><span class="sxs-lookup"><span data-stu-id="a56e9-145">Template String Syntax</span></span>  
 <span data-ttu-id="a56e9-146">Ogni modello presenta tre parti: un percorso, una query facoltativa e un frammento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a56e9-146">A template has three parts: a path, an optional query, and an optional fragment.</span></span> <span data-ttu-id="a56e9-147">Si consideri ad esempio il modello seguente:</span><span class="sxs-lookup"><span data-stu-id="a56e9-147">For an example, see the following template:</span></span>  
  
`"/weather/{state}/{city}?forecast={length)#frag1`  
  
 <span data-ttu-id="a56e9-148">Il percorso è "/previsioni/{regione}/{città}", la query è "?previsioni={durata)" e il frammento è "#framm1".</span><span class="sxs-lookup"><span data-stu-id="a56e9-148">The path consists of "/weather/{state}/{city}", the query consists of "?forecast={length}, and the fragment consists of "#frag1".</span></span>  
  
 <span data-ttu-id="a56e9-149">Le barre iniziali e finali sono facoltative nell'espressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="a56e9-149">Leading and trailing slashes are optional in the path expression.</span></span> <span data-ttu-id="a56e9-150">Le espressioni di query e di frammento possono essere omesse del tutto.</span><span class="sxs-lookup"><span data-stu-id="a56e9-150">Both the query and fragment expressions can be omitted entirely.</span></span> <span data-ttu-id="a56e9-151">Un percorso è costituito da una serie di segmenti delimitati da'/', ogni segmento può avere un valore letterale, un nome di variabile (scritto in {parentesi graffe}) o un carattere jolly (scritto come ' \* ').</span><span class="sxs-lookup"><span data-stu-id="a56e9-151">A path consists of a series of segments delimited by '/', each segment can have a literal value, a variable name (written in {curly braces}), or a wildcard (written as '\*').</span></span> <span data-ttu-id="a56e9-152">Nel modello precedente il segmento "\previsioni\ è un valore letterale, mentre"{regione}" e "{città}" rappresentano variabili.</span><span class="sxs-lookup"><span data-stu-id="a56e9-152">In the previous template the "\weather\ segment is a literal value while "{state}" and "{city}" are variables.</span></span> <span data-ttu-id="a56e9-153">Le variabili prendono il nome dal contenuto delle parentesi graffe e possono essere sostituite in un secondo momento con un valore concreto per creare un *URI chiuso*.</span><span class="sxs-lookup"><span data-stu-id="a56e9-153">Variables take their name from the contents of their curly braces and they can later be replaced with a concrete value to create a *closed URI*.</span></span> <span data-ttu-id="a56e9-154">Il carattere jolly è facoltativo, ma può essere visualizzato solo alla fine dell'URI, dove corrisponde logicamente al resto del percorso.</span><span class="sxs-lookup"><span data-stu-id="a56e9-154">The wildcard is optional, but can only appear at the end of the URI, where it logically matches "the rest of the path".</span></span>  
  
 <span data-ttu-id="a56e9-155">L'espressione di query, se presente, specifica una serie di coppie nome/valore non ordinate delimitate da "&".</span><span class="sxs-lookup"><span data-stu-id="a56e9-155">The query expression, if present, specifies a series of unordered name/value pairs delimited by '&'.</span></span> <span data-ttu-id="a56e9-156">Gli elementi dell'espressione di query possono essere coppie letterali (x=2) o una coppia variabile (x={var}).</span><span class="sxs-lookup"><span data-stu-id="a56e9-156">Elements of the query expression can either be literal pairs (x=2) or a variable pair (x={var}).</span></span> <span data-ttu-id="a56e9-157">Solo il lato destro della query può contenere un'espressione variabile.</span><span class="sxs-lookup"><span data-stu-id="a56e9-157">Only the right side of the query can have a variable expression.</span></span> <span data-ttu-id="a56e9-158">({someName} = {someValue} non è consentito.</span><span class="sxs-lookup"><span data-stu-id="a56e9-158">({someName} = {someValue} is not allowed.</span></span> <span data-ttu-id="a56e9-159">Non è consentito utilizzare valori non abbinati (?x).</span><span class="sxs-lookup"><span data-stu-id="a56e9-159">Unpaired values (?x) are not permitted.</span></span> <span data-ttu-id="a56e9-160">Non c'è differenza tra un'espressione di query vuota e un'espressione di query contenente il solo carattere "?". Entrambe significano infatti "qualsiasi query".</span><span class="sxs-lookup"><span data-stu-id="a56e9-160">There is no difference between an empty query expression and a query expression consisting of just a single '?' (both mean "any query").</span></span>  
  
 <span data-ttu-id="a56e9-161">L'espressione di frammento può essere data da un valore letterale. Non sono consentite le variabili.</span><span class="sxs-lookup"><span data-stu-id="a56e9-161">The fragment expression can consist of a literal value, no variables are allowed.</span></span>  
  
 <span data-ttu-id="a56e9-162">Tutti i nomi variabili del modello contenuti in una stringa di modello devono essere univoci.</span><span class="sxs-lookup"><span data-stu-id="a56e9-162">All template variable names within a template string must be unique.</span></span> <span data-ttu-id="a56e9-163">I nomi variabili del modello non fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="a56e9-163">Template variable names are case-insensitive.</span></span>  
  
 <span data-ttu-id="a56e9-164">Esempi di stringhe di modello valide:</span><span class="sxs-lookup"><span data-stu-id="a56e9-164">Examples of valid template strings:</span></span>  
  
- <span data-ttu-id="a56e9-165">""</span><span class="sxs-lookup"><span data-stu-id="a56e9-165">""</span></span>  
  
- <span data-ttu-id="a56e9-166">"/casa"</span><span class="sxs-lookup"><span data-stu-id="a56e9-166">"/shoe"</span></span>  
  
- <span data-ttu-id="a56e9-167">"/Shoe/ \* "</span><span class="sxs-lookup"><span data-stu-id="a56e9-167">"/shoe/\*"</span></span>  
  
- <span data-ttu-id="a56e9-168">"{casa}/stanza"</span><span class="sxs-lookup"><span data-stu-id="a56e9-168">"{shoe}/boat"</span></span>  
  
- <span data-ttu-id="a56e9-169">"{Shoe}/{Boat}/Bed/{quilt}"</span><span class="sxs-lookup"><span data-stu-id="a56e9-169">"{shoe}/{boat}/bed/{quilt}"</span></span>  
  
- <span data-ttu-id="a56e9-170">"scarpa/{Boat}"</span><span class="sxs-lookup"><span data-stu-id="a56e9-170">"shoe/{boat}"</span></span>  
  
- <span data-ttu-id="a56e9-171">"scarpa/{Boat}/ \* "</span><span class="sxs-lookup"><span data-stu-id="a56e9-171">"shoe/{boat}/\*"</span></span>  
  
- <span data-ttu-id="a56e9-172">"scarpa/barca? x = 2"</span><span class="sxs-lookup"><span data-stu-id="a56e9-172">"shoe/boat?x=2"</span></span>  
  
- <span data-ttu-id="a56e9-173">"scarpa/{Boat}? x = {letto}"</span><span class="sxs-lookup"><span data-stu-id="a56e9-173">"shoe/{boat}?x={bed}"</span></span>  
  
- <span data-ttu-id="a56e9-174">"scarpa/{Boat}? x = {Bed} &y = band"</span><span class="sxs-lookup"><span data-stu-id="a56e9-174">"shoe/{boat}?x={bed}&y=band"</span></span>  
  
- <span data-ttu-id="a56e9-175">"? x = {Shoe}"</span><span class="sxs-lookup"><span data-stu-id="a56e9-175">"?x={shoe}"</span></span>  
  
- <span data-ttu-id="a56e9-176">"scarpa? x = 3&y = {var}</span><span class="sxs-lookup"><span data-stu-id="a56e9-176">"shoe?x=3&y={var}</span></span>  
  
 <span data-ttu-id="a56e9-177">Esempi di stringhe di modello non valide:</span><span class="sxs-lookup"><span data-stu-id="a56e9-177">Examples of invalid template strings:</span></span>  
  
- <span data-ttu-id="a56e9-178">"{Shoe}/{SHOE}/x = 2": nomi di variabili duplicati.</span><span class="sxs-lookup"><span data-stu-id="a56e9-178">"{shoe}/{SHOE}/x=2" – Duplicate variable names.</span></span>  
  
- <span data-ttu-id="a56e9-179">"{Shoe}/Boat/? Bed = {Shoe}": nomi di variabili duplicati.</span><span class="sxs-lookup"><span data-stu-id="a56e9-179">"{shoe}/boat/?bed={shoe}" – Duplicate variable names.</span></span>  
  
- <span data-ttu-id="a56e9-180">"? x = 2&x = 3": le coppie nome/valore all'interno di una stringa di query devono essere univoche, anche se sono valori letterali.</span><span class="sxs-lookup"><span data-stu-id="a56e9-180">"?x=2&x=3" – Name/value pairs within a query string must be unique, even if they are literals.</span></span>  
  
- <span data-ttu-id="a56e9-181">"? x = 2&": il formato della stringa di query non è valido.</span><span class="sxs-lookup"><span data-stu-id="a56e9-181">"?x=2&" – Query string is malformed.</span></span>  
  
- <span data-ttu-id="a56e9-182">"? 2&x = {Shoe}": la stringa di query deve essere costituita da coppie nome/valore.</span><span class="sxs-lookup"><span data-stu-id="a56e9-182">"?2&x={shoe}" – Query string must be name/value pairs.</span></span>  
  
- <span data-ttu-id="a56e9-183">"? y = 2&&X = 3": la stringa di query deve essere costituita da coppie nome-valore. i nomi non possono iniziare con ' &'.</span><span class="sxs-lookup"><span data-stu-id="a56e9-183">"?y=2&&X=3" – Query string must be name value pairs, names cannot start with '&'.</span></span>  
  
### <a name="compound-path-segments"></a><span data-ttu-id="a56e9-184">Segmenti di percorso composti</span><span class="sxs-lookup"><span data-stu-id="a56e9-184">Compound Path Segments</span></span>  
 <span data-ttu-id="a56e9-185">I segmenti di percorso composti consentono a un singolo segmento di percorso URI di contenere più variabili, nonché variabili combinate con valori letterali.</span><span class="sxs-lookup"><span data-stu-id="a56e9-185">Compound path segments allow a single URI path segment to contain multiple variables as well as variables combined with literals.</span></span> <span data-ttu-id="a56e9-186">Di seguito vengono riportati esempi di segmenti di percorso composti validi.</span><span class="sxs-lookup"><span data-stu-id="a56e9-186">The following are examples of valid compound path segments.</span></span>  
  
- <span data-ttu-id="a56e9-187">/nomefile.{ext}/</span><span class="sxs-lookup"><span data-stu-id="a56e9-187">/filename.{ext}/</span></span>  
  
- <span data-ttu-id="a56e9-188">/{nomefile}.jpg/</span><span class="sxs-lookup"><span data-stu-id="a56e9-188">/{filename}.jpg/</span></span>  
  
- <span data-ttu-id="a56e9-189">/{nomefile}.{ext}/</span><span class="sxs-lookup"><span data-stu-id="a56e9-189">/{filename}.{ext}/</span></span>  
  
- <span data-ttu-id="a56e9-190">/{a}.{b}someLiteral{c}({d})/</span><span class="sxs-lookup"><span data-stu-id="a56e9-190">/{a}.{b}someLiteral{c}({d})/</span></span>  
  
 <span data-ttu-id="a56e9-191">Di seguito vengono riportati esempi di segmenti di percorso non validi.</span><span class="sxs-lookup"><span data-stu-id="a56e9-191">The following are examples of invalid path segments.</span></span>  
  
- <span data-ttu-id="a56e9-192">Le {} variabili/-devono essere denominate.</span><span class="sxs-lookup"><span data-stu-id="a56e9-192">/{} - Variables must be named.</span></span>  
  
- <span data-ttu-id="a56e9-193">/{casa}{stanza}: le variabili devono essere separate da un valore letterale.</span><span class="sxs-lookup"><span data-stu-id="a56e9-193">/{shoe}{boat} - Variables must be separated by a literal.</span></span>  
  
### <a name="matching-and-compound-path-segments"></a><span data-ttu-id="a56e9-194">Segmenti di percorso composti e corrispondenti</span><span class="sxs-lookup"><span data-stu-id="a56e9-194">Matching and Compound Path Segments</span></span>  
 <span data-ttu-id="a56e9-195">I segmenti di percorso composti consentono di definire un UriTemplate che dispone di più variabili all'interno di un solo segmento di percorso.</span><span class="sxs-lookup"><span data-stu-id="a56e9-195">Compound path segments allow you to define a UriTemplate that has multiple variables within a single path segment.</span></span> <span data-ttu-id="a56e9-196">Ad esempio, nella stringa di modello seguente: "Addresss/{state}. {City} "due variabili (stato e città) vengono definite all'interno dello stesso segmento.</span><span class="sxs-lookup"><span data-stu-id="a56e9-196">For example, in the following template string: "Addresses/{state}.{city}" two variables (state and city) are defined within the same segment.</span></span> <span data-ttu-id="a56e9-197">Questo modello corrisponderebbe a un URL come, `http://example.com/Washington.Redmond` ma corrisponderà anche a un URL come `http://example.com/Washington.Redmond.Microsoft` .</span><span class="sxs-lookup"><span data-stu-id="a56e9-197">This template would match a URL such as `http://example.com/Washington.Redmond` but it will also match an URL like `http://example.com/Washington.Redmond.Microsoft`.</span></span> <span data-ttu-id="a56e9-198">Nel secondo caso, la variabile di stato conterrà "Washington" e la variabile City conterrà "Redmond. Microsoft".</span><span class="sxs-lookup"><span data-stu-id="a56e9-198">In the latter case, the state variable will contain "Washington" and the city variable will contain "Redmond.Microsoft".</span></span> <span data-ttu-id="a56e9-199">In questo caso il qualsiasi testo (eccetto '/') corrisponderà alla variabile {city}.</span><span class="sxs-lookup"><span data-stu-id="a56e9-199">In this case any text (except ‘/’) will match the {city} variable.</span></span> <span data-ttu-id="a56e9-200">Se si desidera un modello che non corrisponderà al testo "extra", inserire la variabile in un segmento di modello separato, ad esempio: "Addresss/{state}/{City}.</span><span class="sxs-lookup"><span data-stu-id="a56e9-200">If you want a template that will not match the "extra" text, place the variable in a separate template segment, for example: "Addresses/{state}/{city}.</span></span>  
  
### <a name="named-wildcard-segments"></a><span data-ttu-id="a56e9-201">Segmenti con caratteri jolly con nome</span><span class="sxs-lookup"><span data-stu-id="a56e9-201">Named Wildcard Segments</span></span>  
 <span data-ttu-id="a56e9-202">Un segmento con carattere jolly denominato è qualsiasi segmento di variabile di percorso il cui nome di variabile inizia con il carattere jolly " \* ".</span><span class="sxs-lookup"><span data-stu-id="a56e9-202">A named wildcard segment is any path variable segment whose variable name begins with the wildcard character ‘\*’.</span></span> <span data-ttu-id="a56e9-203">La stringa di modello seguente contiene un segmento con carattere jolly con nome denominato "casa".</span><span class="sxs-lookup"><span data-stu-id="a56e9-203">The following template string contains a named wildcard segment named "shoe".</span></span>  
  
`"literal/{*shoe}"`  
  
 <span data-ttu-id="a56e9-204">I segmenti con caratteri jolly devono rispettare le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="a56e9-204">Wildcard segments must follow the following rules:</span></span>  
  
- <span data-ttu-id="a56e9-205">Per ogni stringa di modello può esistere al massimo un segmento con carattere jolly con nome.</span><span class="sxs-lookup"><span data-stu-id="a56e9-205">There can be at most one named wildcard segment for each template string.</span></span>  
  
- <span data-ttu-id="a56e9-206">Un segmento con carattere jolly con nome deve comparire nel segmento all'estrema destra del percorso.</span><span class="sxs-lookup"><span data-stu-id="a56e9-206">A named wildcard segment must appear at the right-most segment in the path.</span></span>  
  
- <span data-ttu-id="a56e9-207">Un segmento con carattere jolly con nome non può coesistere con un segmento con carattere jolly anonimo all'interno della stessa stringa di modello.</span><span class="sxs-lookup"><span data-stu-id="a56e9-207">A named wildcard segment cannot coexist with an anonymous wildcard segment within the same template string.</span></span>  
  
- <span data-ttu-id="a56e9-208">Il nome di un segmento con carattere jolly con nome deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="a56e9-208">The name of a named wildcard segment must be unique.</span></span>  
  
- <span data-ttu-id="a56e9-209">I segmenti con carattere jolly con nome non possono disporre di valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="a56e9-209">Named wildcard segments cannot have default values.</span></span>  
  
- <span data-ttu-id="a56e9-210">I segmenti con carattere jolly con nome non possono terminare con "/".</span><span class="sxs-lookup"><span data-stu-id="a56e9-210">Named wildcard segments cannot end with "/".</span></span>  
  
### <a name="default-variable-values"></a><span data-ttu-id="a56e9-211">Valori di variabili predefiniti</span><span class="sxs-lookup"><span data-stu-id="a56e9-211">Default Variable Values</span></span>  
 <span data-ttu-id="a56e9-212">I valori di variabili predefiniti consentono di specificare valori predefiniti per variabili all'interno di un modello.</span><span class="sxs-lookup"><span data-stu-id="a56e9-212">Default variable values allow you to specify default values for variables within a template.</span></span> <span data-ttu-id="a56e9-213">È possibile specificare le variabili predefinite con parentesi graffe che dichiarano la variabile o come una raccolta passata al costruttore UriTemplate.</span><span class="sxs-lookup"><span data-stu-id="a56e9-213">Default variables can be specified with the curly braces that declare the variable or as a collection passed to the UriTemplate constructor.</span></span> <span data-ttu-id="a56e9-214">Nel modello seguente vengono illustrati due modi per specificare <xref:System.UriTemplate> con variabili con valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="a56e9-214">The following template shows two ways to specify a <xref:System.UriTemplate> with variables with default values.</span></span>  
  
```csharp
UriTemplate t = new UriTemplate("/test/{a=1}/{b=5}");  
```  
  
 <span data-ttu-id="a56e9-215">Questo modello dichiara una variabile denominata `a` con valore predefinito `1` e una variabile denominata `b` con valore predefinito `5`.</span><span class="sxs-lookup"><span data-stu-id="a56e9-215">This template declares a variable named `a` with a default value of `1` and a variable named `b` with a default value of `5`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a56e9-216">Solo le variabili del segmento di percorso possono presentare valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="a56e9-216">Only path segment variables are allowed to have default values.</span></span> <span data-ttu-id="a56e9-217">Le variabili delle stringhe di query, dei segmenti composti e quelle con carattere jolly con nome non possono presentare valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="a56e9-217">Query string variables, compound segment variables, and named wildcard variables are not permitted to have default values.</span></span>  
  
 <span data-ttu-id="a56e9-218">Nell'esempio di codice seguente viene illustrato come gestire i valori di variabili predefiniti quando si crea una corrispondenza con un URI candidato.</span><span class="sxs-lookup"><span data-stu-id="a56e9-218">The following code shows how default variable values are handled when matching a candidate URI.</span></span>  
  
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
> <span data-ttu-id="a56e9-219">Un URI, ad esempio `http://localhost:8000///` , non corrisponde al modello elencato nel codice precedente, tuttavia è un URI come `http://localhost:8000/` .</span><span class="sxs-lookup"><span data-stu-id="a56e9-219">A URI such as `http://localhost:8000///` does not match the template listed in the preceding code, however a URI such as `http://localhost:8000/` does.</span></span>  
  
 <span data-ttu-id="a56e9-220">Nell'esempio di codice seguente viene illustrato come gestire i valori di variabili predefiniti quando si crea un URI con un modello.</span><span class="sxs-lookup"><span data-stu-id="a56e9-220">The following code shows how default variable values are handled when creating a URI with a template.</span></span>  
  
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
  
<span data-ttu-id="a56e9-221">Quando a una variabile viene assegnato il valore predefinito `null`, è necessario tenere conto di alcuni vincoli aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="a56e9-221">When a variable is given a default value of `null` there are some additional constraints.</span></span> <span data-ttu-id="a56e9-222">Una variabile può presentare il valore predefinito `null` se è contenuta nel segmento più a destra della stringa del modello o se tutti i segmenti a destra del segmento presentano valori predefiniti `null`.</span><span class="sxs-lookup"><span data-stu-id="a56e9-222">A variable can have a default value of `null` if the variable is contained within the right most segment of the template string or if all segments to the right of the segment have default values of `null`.</span></span> <span data-ttu-id="a56e9-223">Di seguito vengono riportate stringhe di modello valide con valori predefiniti `null`:</span><span class="sxs-lookup"><span data-stu-id="a56e9-223">The following are valid template strings with default values of `null`:</span></span>  
  
- `UriTemplate t = new UriTemplate("shoe/{boat=null}");`

- `UriTemplate t = new UriTemplate("{shoe=null}/{boat=null}");`
  
- `UriTemplate t = new UriTemplate("{shoe=1}/{boat=null}");`

 <span data-ttu-id="a56e9-224">Di seguito sono riportate stringhe di modello non valide con valori predefiniti `null` :</span><span class="sxs-lookup"><span data-stu-id="a56e9-224">The following are invalid template strings with default values of `null`:</span></span>  
  
- `UriTemplate t = new UriTemplate("{shoe=null}/boat"); // null default must be in the right most path segment`
  
- `UriTemplate t = new UriTemplate("{shoe=null}/{boat=x}/{bed=null}"); // shoe cannot have a null default because boat does not have a default null value`

### <a name="default-values-and-matching"></a><span data-ttu-id="a56e9-225">Valori predefiniti e corrispondenza</span><span class="sxs-lookup"><span data-stu-id="a56e9-225">Default Values and Matching</span></span>  
 <span data-ttu-id="a56e9-226">Quando si crea una corrispondenza tra un URI candidato e un modello con valori predefiniti, se i valori non sono specificati nell'URI candidato i valori predefiniti verranno inseriti nella raccolta <xref:System.UriTemplateMatch.BoundVariables%2A>.</span><span class="sxs-lookup"><span data-stu-id="a56e9-226">When matching a candidate URI with a template that has default values, the default values are placed in the <xref:System.UriTemplateMatch.BoundVariables%2A> collection if values are not specified in the candidate URI.</span></span>  
  
### <a name="template-equivalence"></a><span data-ttu-id="a56e9-227">Equivalenza fra modelli</span><span class="sxs-lookup"><span data-stu-id="a56e9-227">Template Equivalence</span></span>  
 <span data-ttu-id="a56e9-228">Due modelli sono definiti *strutturalmente equivalenti* quando tutti i valori letterali dei modelli corrispondono e hanno variabili negli stessi segmenti.</span><span class="sxs-lookup"><span data-stu-id="a56e9-228">Two templates are said to be *structurally equivalent* when all of the templates' literals match and they have variables in the same segments.</span></span> <span data-ttu-id="a56e9-229">Ad esempio, i modelli seguenti sono strutturalmente equivalenti:</span><span class="sxs-lookup"><span data-stu-id="a56e9-229">For example the following templates are structurally equivalent:</span></span>  
  
- <span data-ttu-id="a56e9-230">/a/{var1}/b b/{var2}? x = 1&y = 2</span><span class="sxs-lookup"><span data-stu-id="a56e9-230">/a/{var1}/b b/{var2}?x=1&y=2</span></span>  
  
- <span data-ttu-id="a56e9-231">a/{x}/b% 20B/{var1}? y = 2&x = 1</span><span class="sxs-lookup"><span data-stu-id="a56e9-231">a/{x}/b%20b/{var1}?y=2&x=1</span></span>  
  
- <span data-ttu-id="a56e9-232">a/{y}/B% 20B/{z}/? y = 2&x = 1</span><span class="sxs-lookup"><span data-stu-id="a56e9-232">a/{y}/B%20B/{z}/?y=2&x=1</span></span>  
  
 <span data-ttu-id="a56e9-233">Alcune considerazioni:</span><span class="sxs-lookup"><span data-stu-id="a56e9-233">A few things to notice:</span></span>  
  
- <span data-ttu-id="a56e9-234">Se un modello contiene barre iniziali, solo la prima viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="a56e9-234">If a template contains leading slashes, only the first one is ignored.</span></span>  
  
- <span data-ttu-id="a56e9-235">Quando si verifica se due stringhe di modello sono strutturalmente equivalenti, i nomi variabili, i segmenti di percorso e le stringhe di query non fanno distinzione fra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="a56e9-235">When comparing template strings for structural equivalence, case is ignored for variable names and path segments, query strings are case sensitive.</span></span>  
  
- <span data-ttu-id="a56e9-236">Le stringhe di query non sono ordinate.</span><span class="sxs-lookup"><span data-stu-id="a56e9-236">Query strings are unordered.</span></span>  
  
## <a name="uritemplatetable"></a><span data-ttu-id="a56e9-237">UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="a56e9-237">UriTemplateTable</span></span>  
 <span data-ttu-id="a56e9-238">La classe <xref:System.UriTemplateTable> rappresenta una tabella associativa di oggetti <xref:System.UriTemplate> associata a un oggetto scelto dallo sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="a56e9-238">The <xref:System.UriTemplateTable> class represents an associative table of <xref:System.UriTemplate> objects bound to an object of the developer's choosing.</span></span> <span data-ttu-id="a56e9-239">Ogni tabella <xref:System.UriTemplateTable> deve contenere almeno un modello <xref:System.UriTemplate> prima di chiamare il metodo <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span><span class="sxs-lookup"><span data-stu-id="a56e9-239">A <xref:System.UriTemplateTable> must contain at least one <xref:System.UriTemplate> prior to calling <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span></span> <span data-ttu-id="a56e9-240">È possibile modificare il contenuto di <xref:System.UriTemplateTable> finché non viene chiamato il metodo <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span><span class="sxs-lookup"><span data-stu-id="a56e9-240">The contents of a <xref:System.UriTemplateTable> can be changed until <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called.</span></span> <span data-ttu-id="a56e9-241">Quando viene chiamato il metodo <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> viene eseguita una convalida</span><span class="sxs-lookup"><span data-stu-id="a56e9-241">Validation is performed when <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called.</span></span> <span data-ttu-id="a56e9-242">il cui tipo dipende dal valore del parametro `allowMultiple` da passare al metodo <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span><span class="sxs-lookup"><span data-stu-id="a56e9-242">The type of validation performed depends upon the value of the `allowMultiple` parameter to <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span></span>  
  
 <span data-ttu-id="a56e9-243">Quando al metodo <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> viene passato il valore `false`, l'oggetto <xref:System.UriTemplateTable> verifica se la tabella contiene modelli.</span><span class="sxs-lookup"><span data-stu-id="a56e9-243">When <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called passing in `false`, the <xref:System.UriTemplateTable> checks to make sure there are no templates in the table.</span></span> <span data-ttu-id="a56e9-244">Se rileva modelli strutturalmente equivalenti, genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="a56e9-244">If it finds any structurally equivalent templates, it throws an exception.</span></span> <span data-ttu-id="a56e9-245">Questo metodo viene utilizzato insieme al metodo <xref:System.UriTemplateTable.MatchSingle%28System.Uri%29> quando si desidera garantire che solo un modello corrisponda a un determinato URI in ingresso.</span><span class="sxs-lookup"><span data-stu-id="a56e9-245">This is used in conjunction with <xref:System.UriTemplateTable.MatchSingle%28System.Uri%29> when you want to ensure only one template matches an incoming URI.</span></span>  
  
 <span data-ttu-id="a56e9-246">Quando viene chiamato il metodo <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> passando `true`, <xref:System.UriTemplateTable> consente la presenza di più modelli strutturalmente equivalenti all'interno di <xref:System.UriTemplateTable>.</span><span class="sxs-lookup"><span data-stu-id="a56e9-246">When <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called passing in `true`, <xref:System.UriTemplateTable> allows multiple, structurally-equivalent templates to be contained within a <xref:System.UriTemplateTable>.</span></span>  
  
 <span data-ttu-id="a56e9-247">Se un set di oggetti <xref:System.UriTemplate> aggiunti a un oggetto <xref:System.UriTemplateTable> contiene stringhe di query, queste non devono essere ambigue.</span><span class="sxs-lookup"><span data-stu-id="a56e9-247">If a set of <xref:System.UriTemplate> objects added to a <xref:System.UriTemplateTable> contain query strings they must not be ambiguous.</span></span> <span data-ttu-id="a56e9-248">È tuttavia consentito utilizzare stringhe di query identiche.</span><span class="sxs-lookup"><span data-stu-id="a56e9-248">Identical query strings are allowed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a56e9-249">Mentre <xref:System.UriTemplateTable> consente la presenza di indirizzi di base che utilizzano schemi diversi da HTTP, lo schema e il numero di porta vengono ignorati quando si creano corrispondenze tra URI candidati e modelli.</span><span class="sxs-lookup"><span data-stu-id="a56e9-249">While the <xref:System.UriTemplateTable> allows base addresses that use schemes other than HTTP, the scheme and port number are ignored when matching candidate URIs to templates.</span></span>  
  
### <a name="query-string-ambiguity"></a><span data-ttu-id="a56e9-250">Ambiguità delle stringhe di query</span><span class="sxs-lookup"><span data-stu-id="a56e9-250">Query String Ambiguity</span></span>  
 <span data-ttu-id="a56e9-251">I modelli che condividono un percorso equivalente contengono stringhe di query ambigue se esiste un URI che corrisponde a più di un modello.</span><span class="sxs-lookup"><span data-stu-id="a56e9-251">Templates that share an equivalent path contain ambiguous query strings if there is a URI that matches more than one template.</span></span>  
  
 <span data-ttu-id="a56e9-252">I set seguenti di stringhe di query non sono ambigui fra loro:</span><span class="sxs-lookup"><span data-stu-id="a56e9-252">The following sets of query strings are unambiguous within themselves:</span></span>  
  
- <span data-ttu-id="a56e9-253">?x=1</span><span class="sxs-lookup"><span data-stu-id="a56e9-253">?x=1</span></span>  
  
- <span data-ttu-id="a56e9-254">?x=2</span><span class="sxs-lookup"><span data-stu-id="a56e9-254">?x=2</span></span>  
  
- <span data-ttu-id="a56e9-255">?x=3</span><span class="sxs-lookup"><span data-stu-id="a56e9-255">?x=3</span></span>  
  
- <span data-ttu-id="a56e9-256">? x = 1&y = {var}</span><span class="sxs-lookup"><span data-stu-id="a56e9-256">?x=1&y={var}</span></span>  
  
- <span data-ttu-id="a56e9-257">? x = 2&z = {var}</span><span class="sxs-lookup"><span data-stu-id="a56e9-257">?x=2&z={var}</span></span>  
  
- <span data-ttu-id="a56e9-258">?x=3</span><span class="sxs-lookup"><span data-stu-id="a56e9-258">?x=3</span></span>  
  
- <span data-ttu-id="a56e9-259">?x=1</span><span class="sxs-lookup"><span data-stu-id="a56e9-259">?x=1</span></span>  
  
- <span data-ttu-id="a56e9-260">?</span><span class="sxs-lookup"><span data-stu-id="a56e9-260">?</span></span>  
  
- <span data-ttu-id="a56e9-261">?</span><span class="sxs-lookup"><span data-stu-id="a56e9-261">?</span></span> <span data-ttu-id="a56e9-262">x={var}</span><span class="sxs-lookup"><span data-stu-id="a56e9-262">x={var}</span></span>  
  
- <span data-ttu-id="a56e9-263">?</span><span class="sxs-lookup"><span data-stu-id="a56e9-263">?</span></span>  
  
- <span data-ttu-id="a56e9-264">? m = Get&c = RSS</span><span class="sxs-lookup"><span data-stu-id="a56e9-264">?m=get&c=rss</span></span>  
  
- <span data-ttu-id="a56e9-265">? m = put&c = RSS</span><span class="sxs-lookup"><span data-stu-id="a56e9-265">?m=put&c=rss</span></span>  
  
- <span data-ttu-id="a56e9-266">? m = Get&c = Atom</span><span class="sxs-lookup"><span data-stu-id="a56e9-266">?m=get&c=atom</span></span>  
  
- <span data-ttu-id="a56e9-267">? m = put&c = Atom</span><span class="sxs-lookup"><span data-stu-id="a56e9-267">?m=put&c=atom</span></span>  
  
 <span data-ttu-id="a56e9-268">I set seguenti di modelli di stringhe di query sono ambigui fra loro:</span><span class="sxs-lookup"><span data-stu-id="a56e9-268">The following sets of query string templates are ambiguous within themselves:</span></span>  
  
- <span data-ttu-id="a56e9-269">?x=1</span><span class="sxs-lookup"><span data-stu-id="a56e9-269">?x=1</span></span>  
  
- <span data-ttu-id="a56e9-270">?x={var}</span><span class="sxs-lookup"><span data-stu-id="a56e9-270">?x={var}</span></span>  
  
 <span data-ttu-id="a56e9-271">"x=1": corrisponde a entrambi i modelli.</span><span class="sxs-lookup"><span data-stu-id="a56e9-271">"x=1" - Matches both templates.</span></span>  
  
- <span data-ttu-id="a56e9-272">?x=1</span><span class="sxs-lookup"><span data-stu-id="a56e9-272">?x=1</span></span>  
  
- <span data-ttu-id="a56e9-273">?y=2</span><span class="sxs-lookup"><span data-stu-id="a56e9-273">?y=2</span></span>  
  
 <span data-ttu-id="a56e9-274">"x = 1&y = 2" corrisponde a entrambi i modelli.</span><span class="sxs-lookup"><span data-stu-id="a56e9-274">"x=1&y=2" matches both templates.</span></span> <span data-ttu-id="a56e9-275">Ciò è dovuto al fatto che una stringa di query può contenere più variabili di stringa rispetto al modello a cui corrisponde.</span><span class="sxs-lookup"><span data-stu-id="a56e9-275">This is because a query string may contain more query string variables then the template it matches.</span></span>  
  
- <span data-ttu-id="a56e9-276">?x=1</span><span class="sxs-lookup"><span data-stu-id="a56e9-276">?x=1</span></span>  
  
- <span data-ttu-id="a56e9-277">? x = 1&y = {var}</span><span class="sxs-lookup"><span data-stu-id="a56e9-277">?x=1&y={var}</span></span>  
  
 <span data-ttu-id="a56e9-278">"x = 1&y = 3" corrisponde a entrambi i modelli.</span><span class="sxs-lookup"><span data-stu-id="a56e9-278">"x=1&y=3" matches both templates.</span></span>  
  
- <span data-ttu-id="a56e9-279">? x = 3&y = 4</span><span class="sxs-lookup"><span data-stu-id="a56e9-279">?x=3&y=4</span></span>  
  
- <span data-ttu-id="a56e9-280">? x = 3&z = 5</span><span class="sxs-lookup"><span data-stu-id="a56e9-280">?x=3&z=5</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a56e9-281">I caratteri á e Á sono considerati caratteri diversi quando vengono visualizzati come parte di un percorso URI o di un <xref:System.UriTemplate> valore letterale del segmento di percorso (ma i caratteri a e a sono considerati uguali).</span><span class="sxs-lookup"><span data-stu-id="a56e9-281">The characters á and Á are considered to be different characters when they appear as part of a URI path or <xref:System.UriTemplate> path segment literal (but the characters a and A are considered to be the same).</span></span> <span data-ttu-id="a56e9-282">I caratteri á e Á sono considerati gli stessi caratteri quando vengono visualizzati come parte di un <xref:System.UriTemplate> {variablename} o una stringa di query (e un oggetto e un oggetto sono considerati anche gli stessi caratteri).</span><span class="sxs-lookup"><span data-stu-id="a56e9-282">The characters á and Á are considered to be the same characters when they appear as part of a <xref:System.UriTemplate> {variableName} or a query string (and a and A are also considered to be the same characters).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a56e9-283">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="a56e9-283">See also</span></span>

- [<span data-ttu-id="a56e9-284">Panoramica sul modello di programmazione HTTP Web WCF</span><span class="sxs-lookup"><span data-stu-id="a56e9-284">WCF Web HTTP Programming Model Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)
- [<span data-ttu-id="a56e9-285">Modello a oggetti per la programmazione HTTP Web di WCF</span><span class="sxs-lookup"><span data-stu-id="a56e9-285">WCF Web HTTP Programming Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md)
- [<span data-ttu-id="a56e9-286">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="a56e9-286">UriTemplate</span></span>](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
- [<span data-ttu-id="a56e9-287">UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="a56e9-287">UriTemplate Table</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)
- [<span data-ttu-id="a56e9-288">Dispatcher della tabella UriTemplate</span><span class="sxs-lookup"><span data-stu-id="a56e9-288">UriTemplate Table Dispatcher</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)
