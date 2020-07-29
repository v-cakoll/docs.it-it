---
title: Guida alla sicurezza di BinaryFormatter
description: In questo articolo vengono descritti i rischi di sicurezza inerenti al tipo BinaryFormatter e i consigli per i diversi serializzatori da utilizzare.
ms.date: 07/11/2020
ms.author: levib
author: GrabYourPitchforks
ms.openlocfilehash: f6a54b34bbf1e19212fe37aadb448a1722fe9ff0
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2020
ms.locfileid: "86444766"
---
# <a name="binaryformatter-security-guide"></a><span data-ttu-id="8a204-103">Guida alla sicurezza di BinaryFormatter</span><span class="sxs-lookup"><span data-stu-id="8a204-103">BinaryFormatter security guide</span></span>

<span data-ttu-id="8a204-104">Questo articolo si applica alle seguenti implementazioni di .NET:</span><span class="sxs-lookup"><span data-stu-id="8a204-104">This article applies to the following .NET implementations:</span></span>

* <span data-ttu-id="8a204-105">.NET Framework tutte le versioni</span><span class="sxs-lookup"><span data-stu-id="8a204-105">.NET Framework all versions</span></span>
* <span data-ttu-id="8a204-106">.NET Core 2,1-3,1</span><span class="sxs-lookup"><span data-stu-id="8a204-106">.NET Core 2.1 - 3.1</span></span>
* <span data-ttu-id="8a204-107">.NET 5,0 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="8a204-107">.NET 5.0 and later</span></span>

## <a name="background"></a><span data-ttu-id="8a204-108">Background</span><span class="sxs-lookup"><span data-stu-id="8a204-108">Background</span></span>

> [!WARNING]
> <span data-ttu-id="8a204-109">Il <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> tipo è pericoloso ed è ***sconsigliato*** per l'elaborazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="8a204-109">The <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> type is dangerous and is ***not*** recommended for data processing.</span></span> <span data-ttu-id="8a204-110">Le applicazioni devono smettere di usare `BinaryFormatter` il prima possibile, anche se ritengono che i dati che stanno elaborando siano affidabili.</span><span class="sxs-lookup"><span data-stu-id="8a204-110">Applications should stop using `BinaryFormatter` as soon as possible, even if they believe the data they're processing to be trustworthy.</span></span> <span data-ttu-id="8a204-111">`BinaryFormatter`non può essere protetto in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="8a204-111">`BinaryFormatter` is insecure can't be made secure.</span></span>

<span data-ttu-id="8a204-112">Questo articolo si applica anche ai tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a204-112">This article also applies to the following types:</span></span>

* <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>
* <xref:System.Runtime.Serialization.NetDataContractSerializer>
* <xref:System.Web.UI.LosFormatter>
* <xref:System.Web.UI.ObjectStateFormatter>

<span data-ttu-id="8a204-113">Le vulnerabilità di deserializzazione sono una categoria di minacce in cui i payload delle richieste vengono elaborati in modo non sicuro.</span><span class="sxs-lookup"><span data-stu-id="8a204-113">Deserialization vulnerabilities are a threat category where request payloads are processed insecurely.</span></span> <span data-ttu-id="8a204-114">Un utente malintenzionato che usa correttamente queste vulnerabilità in un'app può causare attacchi di tipo Denial of Service (DoS), divulgazione di informazioni o esecuzione di codice in modalità remota all'interno dell'app di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8a204-114">An attacker who successfully leverages these vulnerabilities against an app can cause denial of service (DoS), information disclosure, or remote code execution inside the target app.</span></span> <span data-ttu-id="8a204-115">Questa categoria di rischio rende coerenti le [prime 10 OWASP](https://owasp.org/www-project-top-ten/).</span><span class="sxs-lookup"><span data-stu-id="8a204-115">This risk category consistently makes the [OWASP Top 10](https://owasp.org/www-project-top-ten/).</span></span> <span data-ttu-id="8a204-116">Le destinazioni includono app scritte in [un'ampia gamma di linguaggi](https://owasp.org/www-community/vulnerabilities/Deserialization_of_untrusted_data), tra cui C/C++, Java e C#.</span><span class="sxs-lookup"><span data-stu-id="8a204-116">Targets include apps written in [a variety of languages](https://owasp.org/www-community/vulnerabilities/Deserialization_of_untrusted_data), including C/C++, Java, and C#.</span></span>

<span data-ttu-id="8a204-117">In .NET, la destinazione di rischio maggiore è rappresentata dalle app che usano il <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> tipo per deserializzare i dati.</span><span class="sxs-lookup"><span data-stu-id="8a204-117">In .NET, the biggest risk target is apps that use the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> type to deserialize data.</span></span> <span data-ttu-id="8a204-118">`BinaryFormatter`viene ampiamente usato nell'ecosistema .NET grazie alla potenza e alla semplicità d'uso.</span><span class="sxs-lookup"><span data-stu-id="8a204-118">`BinaryFormatter` is widely used throughout the .NET ecosystem because of its power and its ease of use.</span></span> <span data-ttu-id="8a204-119">Tuttavia, questa stessa alimentazione offre agli utenti malintenzionati la possibilità di influenzare il flusso di controllo all'interno dell'app di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8a204-119">However, this same power gives attackers the ability to influence control flow within the target app.</span></span> <span data-ttu-id="8a204-120">Gli attacchi riusciti possono comportare che l'utente malintenzionato sia in grado di eseguire il codice nel contesto del processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8a204-120">Successful attacks can result in the attacker being able to run code within the context of the target process.</span></span>

<span data-ttu-id="8a204-121">Come analogia più semplice, si supponga che `BinaryFormatter.Deserialize` la chiamata su un payload equivale a interpretare il payload come eseguibile autonomo e come avviarlo.</span><span class="sxs-lookup"><span data-stu-id="8a204-121">As a simpler analogy, assume that calling `BinaryFormatter.Deserialize` over a payload is the equivalent of interpreting that payload as a standalone executable and launching it.</span></span>

## <a name="binaryformatter-security-vulnerabilities"></a><span data-ttu-id="8a204-122">Vulnerabilità della sicurezza di BinaryFormatter</span><span class="sxs-lookup"><span data-stu-id="8a204-122">BinaryFormatter security vulnerabilities</span></span>

> [!WARNING]
> <span data-ttu-id="8a204-123">Il `BinaryFormatter.Deserialize` metodo __non è mai__ sicuro se usato con input non attendibile.</span><span class="sxs-lookup"><span data-stu-id="8a204-123">The `BinaryFormatter.Deserialize` method is __never__ safe when used with untrusted input.</span></span> <span data-ttu-id="8a204-124">È consigliabile che i consumer considerino invece una delle alternative descritte più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="8a204-124">We strongly recommend that consumers instead consider using one of the alternatives outlined later in this article.</span></span>

<span data-ttu-id="8a204-125">`BinaryFormatter`è stato implementato prima che le vulnerabilità di deserializzazione fossero una categoria di minacce ben riconosciuta.</span><span class="sxs-lookup"><span data-stu-id="8a204-125">`BinaryFormatter` was implemented before deserialization vulnerabilities were a well-understood threat category.</span></span> <span data-ttu-id="8a204-126">Di conseguenza, il codice non segue le procedure consigliate moderne.</span><span class="sxs-lookup"><span data-stu-id="8a204-126">As a result, the code does not follow modern best practices.</span></span> <span data-ttu-id="8a204-127">Il `Deserialize` metodo può essere usato come vettore per impedire agli utenti malintenzionati di eseguire attacchi DOS contro l'utilizzo di app.</span><span class="sxs-lookup"><span data-stu-id="8a204-127">The `Deserialize` method can be used as a vector for attackers to perform DoS attacks against consuming apps.</span></span> <span data-ttu-id="8a204-128">Questi attacchi potrebbero rendere l'applicazione non risponde o comportare una chiusura imprevista del processo.</span><span class="sxs-lookup"><span data-stu-id="8a204-128">These attacks might render the app unresponsive or result in unexpected process termination.</span></span> <span data-ttu-id="8a204-129">Non è possibile mitigare questa categoria di attacchi con una `SerializationBinder` o con altre `BinaryFormatter` Opzioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="8a204-129">This category of attack cannot be mitigated with a `SerializationBinder` or any other `BinaryFormatter` configuration switch.</span></span> <span data-ttu-id="8a204-130">.NET considera questo comportamento come ***da progettazione*** e non emette un aggiornamento del codice per modificare il comportamento.</span><span class="sxs-lookup"><span data-stu-id="8a204-130">.NET considers this behavior to be ***by design*** and won't issue a code update to modify the behavior.</span></span>

<span data-ttu-id="8a204-131">`BinaryFormatter.Deserialize`potrebbe essere vulnerabile ad altre categorie di attacchi, ad esempio la divulgazione di informazioni o l'esecuzione di codice in modalità remota.</span><span class="sxs-lookup"><span data-stu-id="8a204-131">`BinaryFormatter.Deserialize` may be vulnerable to other attack categories, such as information disclosure or remote code execution.</span></span> <span data-ttu-id="8a204-132">L'utilizzo di funzionalità come una personalizzata <xref:System.Runtime.Serialization.SerializationBinder> potrebbe non essere sufficiente per attenuare correttamente questi rischi.</span><span class="sxs-lookup"><span data-stu-id="8a204-132">Utilizing features such as a custom <xref:System.Runtime.Serialization.SerializationBinder> may be insufficient to properly mitigate these risks.</span></span> <span data-ttu-id="8a204-133">Esiste la possibilità che venga individuata una nuova vulnerabilità per cui .NET non è in grado di pubblicare un aggiornamento della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8a204-133">The possibility exists that a novel vulnerability will be discovered for which .NET cannot practically publish a security update.</span></span> <span data-ttu-id="8a204-134">I consumer devono valutare i singoli scenari e prendere in considerazione la loro potenziale esposizione a questi rischi.</span><span class="sxs-lookup"><span data-stu-id="8a204-134">Consumers should assess their individual scenarios and consider their potential exposure to these risks.</span></span>

<span data-ttu-id="8a204-135">È consigliabile che `BinaryFormatter` i consumer eseguano valutazioni dei rischi individuali sulle app.</span><span class="sxs-lookup"><span data-stu-id="8a204-135">We recommend that `BinaryFormatter` consumers perform individual risk assessments on their apps.</span></span> <span data-ttu-id="8a204-136">È responsabilità dell'utente determinare se usare `BinaryFormatter` .</span><span class="sxs-lookup"><span data-stu-id="8a204-136">It is the consumer's sole responsibility to determine whether to utilize `BinaryFormatter`.</span></span> <span data-ttu-id="8a204-137">I consumer dovrebbero valutare i requisiti di sicurezza, tecnici, di reputazione, legali e normativi dell'uso di `BinaryFormatter` .</span><span class="sxs-lookup"><span data-stu-id="8a204-137">Consumers should risk assess the security, technical, reputation, legal, and regulatory requirements of using `BinaryFormatter`.</span></span>

## <a name="preferred-alternatives"></a><span data-ttu-id="8a204-138">Alternative preferite</span><span class="sxs-lookup"><span data-stu-id="8a204-138">Preferred alternatives</span></span>

<span data-ttu-id="8a204-139">.NET offre diversi serializzatori in-box che possono gestire i dati non attendibili in modo sicuro:</span><span class="sxs-lookup"><span data-stu-id="8a204-139">.NET offers several in-box serializers that can handle untrusted data safely:</span></span>

* <span data-ttu-id="8a204-140"><xref:System.Xml.Serialization.XmlSerializer>e <xref:System.Runtime.Serialization.DataContractSerializer> per serializzare gli oggetti grafici in e da XML.</span><span class="sxs-lookup"><span data-stu-id="8a204-140"><xref:System.Xml.Serialization.XmlSerializer> and <xref:System.Runtime.Serialization.DataContractSerializer> to serialize object graphs into and from XML.</span></span> <span data-ttu-id="8a204-141">Non confondere `DataContractSerializer` con <xref:System.Runtime.Serialization.NetDataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="8a204-141">Do not confuse `DataContractSerializer` with  <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span>
* <span data-ttu-id="8a204-142"><xref:System.IO.BinaryReader>e <xref:System.IO.BinaryWriter> per XML e JSON.</span><span class="sxs-lookup"><span data-stu-id="8a204-142"><xref:System.IO.BinaryReader> and <xref:System.IO.BinaryWriter> for XML and JSON.</span></span>
* <span data-ttu-id="8a204-143"><xref:System.Text.Json>API per la serializzazione di oggetti grafici in JSON.</span><span class="sxs-lookup"><span data-stu-id="8a204-143">The <xref:System.Text.Json> APIs to serialize object graphs into JSON.</span></span>

## <a name="dangerous-alternatives"></a><span data-ttu-id="8a204-144">Alternative pericolose</span><span class="sxs-lookup"><span data-stu-id="8a204-144">Dangerous alternatives</span></span>

<span data-ttu-id="8a204-145">Evitare i serializzatori seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a204-145">Avoid the following serializers:</span></span>

* <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>
* <xref:System.Web.UI.LosFormatter>
* <xref:System.Runtime.Serialization.NetDataContractSerializer>
* <xref:System.Web.UI.ObjectStateFormatter>

<span data-ttu-id="8a204-146">I serializzatori precedenti eseguono tutte la deserializzazione polimorfica senza restrizioni e sono pericolose, proprio come `BinaryFormatter` .</span><span class="sxs-lookup"><span data-stu-id="8a204-146">The preceding serializers all perform unrestricted polymorphic deserialization and are dangerous, just like `BinaryFormatter`.</span></span>

## <a name="the-risks-of-assuming-data-to-be-trustworthy"></a><span data-ttu-id="8a204-147">Rischi derivanti dal presupposto che i dati siano affidabili</span><span class="sxs-lookup"><span data-stu-id="8a204-147">The risks of assuming data to be trustworthy</span></span>

<span data-ttu-id="8a204-148">Spesso, uno sviluppatore di app potrebbe ritenere che stiano elaborando solo un input attendibile.</span><span class="sxs-lookup"><span data-stu-id="8a204-148">Frequently, an app developer might believe that they are processing only trusted input.</span></span> <span data-ttu-id="8a204-149">Il caso di input sicuro è true in alcune circostanze rare.</span><span class="sxs-lookup"><span data-stu-id="8a204-149">The safe input case is true in some rare circumstances.</span></span> <span data-ttu-id="8a204-150">Ma è molto più comune che un payload attraversi un confine di trust senza che lo sviluppatore lo realizzi.</span><span class="sxs-lookup"><span data-stu-id="8a204-150">But it's much more common that a payload crosses a trust boundary without the developer realizing it.</span></span>

<span data-ttu-id="8a204-151">Si __consideri un server locale in__ cui i dipendenti usano un client desktop dalle rispettive workstation per interagire con il servizio.</span><span class="sxs-lookup"><span data-stu-id="8a204-151">__Consider an on-prem server__ where employees use a desktop client from their workstations to interact with the service.</span></span> <span data-ttu-id="8a204-152">Questo scenario può essere considerato ingenuamente come un programma di installazione "sicuro" in cui l'utilizzo `BinaryFormatter` è accettabile.</span><span class="sxs-lookup"><span data-stu-id="8a204-152">This scenario might be seen naïvely as a "safe" setup where utilizing `BinaryFormatter` is acceptable.</span></span> <span data-ttu-id="8a204-153">Tuttavia, questo scenario presenta un vettore per il malware che ottiene l'accesso al computer di un singolo dipendente per potersi diffondere nell'intera azienda.</span><span class="sxs-lookup"><span data-stu-id="8a204-153">However, this scenario presents a vector for malware that gains access to a single employee's machine to be able to spread throughout the enterprise.</span></span> <span data-ttu-id="8a204-154">Il malware può sfruttare l'uso dell'azienda di `BinaryFormatter` per spostarsi lateralmente dalla workstation del dipendente al server back-end.</span><span class="sxs-lookup"><span data-stu-id="8a204-154">That malware can leverage the enterprise's use of `BinaryFormatter` to move laterally from the employee's workstation to the backend server.</span></span> <span data-ttu-id="8a204-155">Può quindi sottrarre i dati sensibili della società.</span><span class="sxs-lookup"><span data-stu-id="8a204-155">It can then exfiltrate the company's sensitive data.</span></span> <span data-ttu-id="8a204-156">Tali dati possono includere segreti commerciali o dati dei clienti.</span><span class="sxs-lookup"><span data-stu-id="8a204-156">Such data could include trade secrets or customer data.</span></span>

<span data-ttu-id="8a204-157">__Si consideri anche un'app che usa `BinaryFormatter` per salvare in modo permanente lo stato.__</span><span class="sxs-lookup"><span data-stu-id="8a204-157">__Consider also an app that uses `BinaryFormatter` to persist save state.__</span></span> <span data-ttu-id="8a204-158">Questo potrebbe sembrare inizialmente uno scenario sicuro, perché la lettura e la scrittura dei dati sul disco rigido rappresentano una minaccia secondaria.</span><span class="sxs-lookup"><span data-stu-id="8a204-158">This might at first seem to be a safe scenario, as reading and writing data on your own hard drive represents a minor threat.</span></span> <span data-ttu-id="8a204-159">Tuttavia, la condivisione di documenti attraverso la posta elettronica o Internet è comune e la maggior parte degli utenti finali non può percepire l'apertura di questi file scaricati come comportamento rischioso.</span><span class="sxs-lookup"><span data-stu-id="8a204-159">However, sharing documents across email or the internet is common, and most end users wouldn't perceive opening these downloaded files as risky behavior.</span></span>

<span data-ttu-id="8a204-160">Questo scenario può essere sfruttato per effetto nefasto.</span><span class="sxs-lookup"><span data-stu-id="8a204-160">This scenario can be leveraged to nefarious effect.</span></span> <span data-ttu-id="8a204-161">Se l'app è un gioco, gli utenti che condividono i file di salvataggio inconsapevolmente si trovano a rischio.</span><span class="sxs-lookup"><span data-stu-id="8a204-161">If the app is a game, users who share save files unknowingly place themselves at risk.</span></span> <span data-ttu-id="8a204-162">Gli sviluppatori possono anche essere assegnati.</span><span class="sxs-lookup"><span data-stu-id="8a204-162">The developers themselves can also be targeted.</span></span> <span data-ttu-id="8a204-163">L'autore dell'attacco potrebbe inviare un messaggio di posta elettronica al supporto tecnico degli sviluppatori, collegando un file di dati dannosi e chiedendo al personale del supporto di aprirlo.</span><span class="sxs-lookup"><span data-stu-id="8a204-163">The attacker might email the developers' tech support, attaching a malicious data file and asking the support staff to open it.</span></span> <span data-ttu-id="8a204-164">Questo tipo di attacco potrebbe dare all'utente malintenzionato un punto di appoggio nell'azienda.</span><span class="sxs-lookup"><span data-stu-id="8a204-164">This kind of attack could give the attacker a foothold in the enterprise.</span></span>

<span data-ttu-id="8a204-165">Un altro scenario è la posizione in cui il file di dati viene archiviato nella memoria cloud e sincronizzato automaticamente tra i computer dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8a204-165">Another scenario is where the data file is stored in cloud storage and automatically synced between the user's machines.</span></span> <span data-ttu-id="8a204-166">Un utente malintenzionato che è in grado di ottenere l'accesso all'account di archiviazione cloud può avvelenare il file di dati.</span><span class="sxs-lookup"><span data-stu-id="8a204-166">An attacker who is able to gain access to the cloud storage account can poison the data file.</span></span> <span data-ttu-id="8a204-167">Questo file di dati verrà sincronizzato automaticamente con i computer dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8a204-167">This data file will be automatically synced to the user's machines.</span></span> <span data-ttu-id="8a204-168">Alla successiva apertura del file di dati da parte dell'utente, viene eseguito il payload del pirata informatico.</span><span class="sxs-lookup"><span data-stu-id="8a204-168">The next time the user opens the data file, the attacker's payload runs.</span></span> <span data-ttu-id="8a204-169">Pertanto, l'autore dell'attacco può sfruttare la compromissione di un account di archiviazione cloud per ottenere le autorizzazioni di esecuzione del codice completo.</span><span class="sxs-lookup"><span data-stu-id="8a204-169">Thus the attacker can leverage a cloud storage account compromise to gain full code execution permissions.</span></span>

<span data-ttu-id="8a204-170">__Si consideri un'app che passa da un modello di installazione desktop a un modello cloud-First.__</span><span class="sxs-lookup"><span data-stu-id="8a204-170">__Consider an app that moves from a desktop-install model to a cloud-first model.__</span></span> <span data-ttu-id="8a204-171">Questo scenario include le app che passano da un'app desktop o un modello rich client in un modello basato sul Web.</span><span class="sxs-lookup"><span data-stu-id="8a204-171">This scenario includes apps that move from a desktop app or rich client model into a web-based model.</span></span> <span data-ttu-id="8a204-172">Tutti i modelli di rischio creati per l'app desktop non sono necessariamente applicabili al servizio basato sul cloud.</span><span class="sxs-lookup"><span data-stu-id="8a204-172">Any threat models drawn for the desktop app aren't necessarily applicable to the cloud-based service.</span></span> <span data-ttu-id="8a204-173">Il modello di minaccia per l'app desktop potrebbe ignorare una determinata minaccia come "non interessante per il client di attaccare se stesso".</span><span class="sxs-lookup"><span data-stu-id="8a204-173">The threat model for the desktop app might dismiss a given threat as "not interesting for the client to attack itself."</span></span> <span data-ttu-id="8a204-174">Tuttavia, la stessa minaccia potrebbe diventare interessante quando considera un utente remoto (il client) che attacca il servizio cloud.</span><span class="sxs-lookup"><span data-stu-id="8a204-174">But that same threat might become interesting when it considers a remote user (the client) attacking the cloud service itself.</span></span>

> [!NOTE]
> <span data-ttu-id="8a204-175">In termini generali, lo scopo della serializzazione è trasmettere un oggetto all'interno o all'esterno di un'app.</span><span class="sxs-lookup"><span data-stu-id="8a204-175">In general terms, the intent of serialization is to transmit an object into or out of an app.</span></span> <span data-ttu-id="8a204-176">Un esercizio di modellazione delle minacce contrassegna quasi sempre questo tipo di trasferimento dei dati come superamento di un confine di trust.</span><span class="sxs-lookup"><span data-stu-id="8a204-176">A threat modeling exercise almost always marks this kind of data transfer as crossing a trust boundary.</span></span>

## <a name="further-resources"></a><span data-ttu-id="8a204-177">Altre risorse</span><span class="sxs-lookup"><span data-stu-id="8a204-177">Further resources</span></span>

* <span data-ttu-id="8a204-178">[YSoSerial.NET](https://github.com/pwntester/ysoserial.net) per la ricerca di come gli avversari attaccano le app che usano `BinaryFormatter` .</span><span class="sxs-lookup"><span data-stu-id="8a204-178">[YSoSerial.Net](https://github.com/pwntester/ysoserial.net) for research into how adversaries attack apps that utilize `BinaryFormatter`.</span></span>
* <span data-ttu-id="8a204-179">[Modellazione delle minacce](/securityengineering/sdl/threatmodeling) per informazioni sulle app e i servizi di modellazione delle minacce.</span><span class="sxs-lookup"><span data-stu-id="8a204-179">[Threat Modeling](/securityengineering/sdl/threatmodeling) for information on threat modeling apps and services.</span></span>
* <span data-ttu-id="8a204-180">Background generale sulle vulnerabilità di deserializzazione:</span><span class="sxs-lookup"><span data-stu-id="8a204-180">General background on deserialization vulnerabilities:</span></span>
  * [<span data-ttu-id="8a204-181">OWASP Top 10-A8:2017-deserializzazione non sicura</span><span class="sxs-lookup"><span data-stu-id="8a204-181">OWASP Top 10 - A8:2017-Insecure Deserialization</span></span>](https://owasp.org/www-project-top-ten/OWASP_Top_Ten_2017/Top_10-2017_A8-Insecure_Deserialization)
  * [<span data-ttu-id="8a204-182">CWE-502: deserializzazione di dati non attendibili</span><span class="sxs-lookup"><span data-stu-id="8a204-182">CWE-502: Deserialization of Untrusted Data</span></span>](https://cwe.mitre.org/data/definitions/502.html)