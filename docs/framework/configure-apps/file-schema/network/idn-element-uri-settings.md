---
title: Elemento <idn> (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
ms.openlocfilehash: 5fe2eafee702be96bfdca80a06af4a040d9ef0f6
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664129"
---
# <a name="idn-element-uri-settings"></a><span data-ttu-id="251a8-102">\<Elemento > IDN (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="251a8-102">\<idn> Element (Uri Settings)</span></span>
<span data-ttu-id="251a8-103">Specifica se l'analisi del nome di dominio internazionale (IDN) viene applicata a un nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="251a8-103">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="251a8-104">Gerarchia dello schema</span><span class="sxs-lookup"><span data-stu-id="251a8-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="251a8-105">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="251a8-105">\<configuration> Element</span></span>](../configuration-element.md)  
  
 [<span data-ttu-id="251a8-106">\<Elemento > URI (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="251a8-106">\<Uri> Element (Uri Settings)</span></span>](uri-element-uri-settings.md)  
  
 [<span data-ttu-id="251a8-107">\<idn></span><span class="sxs-lookup"><span data-stu-id="251a8-107">\<idn></span></span>](idn-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="251a8-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="251a8-108">Syntax</span></span>  
  
```xml  
<idn  
  enabled="All|AllExceptIntranet|None"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="251a8-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="251a8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="251a8-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="251a8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="251a8-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="251a8-111">Attributes</span></span>  
  
|<span data-ttu-id="251a8-112">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="251a8-112">**Element**</span></span>|<span data-ttu-id="251a8-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="251a8-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="251a8-114">Specifica se l'analisi del nome di dominio internazionale (IDN) viene applicata a un nome di dominio. il valore predefinito è None.</span><span class="sxs-lookup"><span data-stu-id="251a8-114">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name The default value is none.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="251a8-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="251a8-115">Child Elements</span></span>  
 <span data-ttu-id="251a8-116">Nessuna</span><span class="sxs-lookup"><span data-stu-id="251a8-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="251a8-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="251a8-117">Parent Elements</span></span>  
  
|<span data-ttu-id="251a8-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="251a8-118">**Element**</span></span>|<span data-ttu-id="251a8-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="251a8-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="251a8-120">uri</span><span class="sxs-lookup"><span data-stu-id="251a8-120">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="251a8-121">Contiene le impostazioni che specificano il modo in cui il .NET Framework gestisce gli indirizzi Web espressi tramite URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="251a8-121">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="251a8-122">Note</span><span class="sxs-lookup"><span data-stu-id="251a8-122">Remarks</span></span>  
 <span data-ttu-id="251a8-123">La classe <xref:System.Uri> esistente è stata estesa in .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="251a8-123">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="251a8-124">3,0 SP1 e 2,0 SP1 con supporto per gli identificatori di risorse internazionali (IRI) e i nomi di dominio internazionali (IDN).</span><span class="sxs-lookup"><span data-stu-id="251a8-124">3.0 SP1, and 2.0 SP1 with support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="251a8-125">Gli utenti correnti non vedranno alcuna modifica rispetto al comportamento di .NET Framework 2,0, a meno che non vengano specificamente abilitati il supporto di IRI e IDN.</span><span class="sxs-lookup"><span data-stu-id="251a8-125">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="251a8-126">Questo garantisce la compatibilità delle applicazioni con le versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="251a8-126">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="251a8-127">Per abilitare il supporto per IRI, sono necessarie le due modifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="251a8-127">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="251a8-128">Aggiungere la riga seguente al file Machine. config nella directory .NET Framework 2,0</span><span class="sxs-lookup"><span data-stu-id="251a8-128">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="251a8-129">Specificare se si desidera che l'analisi del nome di dominio internazionalizzazione (IDN) venga applicata al nome di dominio e se devono essere applicate le regole di analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="251a8-129">Specify whether you want Internationalized Domain Name (IDN) parsing applied to the domain name and whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="251a8-130">A questo scopo, è possibile usare il file machine.config o il file app.config.</span><span class="sxs-lookup"><span data-stu-id="251a8-130">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="251a8-131">Esistono tre possibili valori per IDN a seconda dei server DNS utilizzati:</span><span class="sxs-lookup"><span data-stu-id="251a8-131">There are three possible values for IDN depending on the DNS servers that are used:</span></span>  
  
- <span data-ttu-id="251a8-132">IDN abilitato = tutti</span><span class="sxs-lookup"><span data-stu-id="251a8-132">idn enabled = All</span></span>  
  
     <span data-ttu-id="251a8-133">Questo valore convertirà i nomi di dominio Unicode negli equivalenti Punycode (nomi IDN).</span><span class="sxs-lookup"><span data-stu-id="251a8-133">This value will convert any Unicode domain names to their Punycode equivalents (IDN names).</span></span>  
  
- <span data-ttu-id="251a8-134">IDN abilitato = AllExceptIntranet</span><span class="sxs-lookup"><span data-stu-id="251a8-134">idn enabled = AllExceptIntranet</span></span>  
  
     <span data-ttu-id="251a8-135">Questo valore convertirà tutti i nomi di dominio Unicode non presenti nella rete Intranet locale per utilizzare gli equivalenti Punycode (nomi IDN).</span><span class="sxs-lookup"><span data-stu-id="251a8-135">This value will convert all Unicode domain names not on the local Intranet to use the Punycode equivalents (IDN names).</span></span> <span data-ttu-id="251a8-136">In questo caso, per gestire i nomi internazionali sulla Intranet locale, i server DNS utilizzati per la Intranet devono supportare la risoluzione dei nomi Unicode.</span><span class="sxs-lookup"><span data-stu-id="251a8-136">In this case to handle international names on the local Intranet, the DNS servers that are used for the Intranet should support Unicode name resolution.</span></span>  
  
- <span data-ttu-id="251a8-137">IDN abilitato = None</span><span class="sxs-lookup"><span data-stu-id="251a8-137">idn enabled = None</span></span>  
  
     <span data-ttu-id="251a8-138">Con questo valore non verrà convertito alcun nome di dominio Unicode per l'utilizzo di Punycode.</span><span class="sxs-lookup"><span data-stu-id="251a8-138">This value will not convert any Unicode domain names to use Punycode.</span></span> <span data-ttu-id="251a8-139">Si tratta del valore predefinito, coerente con il comportamento .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="251a8-139">This is the default value which is consistent with the .NET Framework 2.0 behaviour.</span></span>  
  
 <span data-ttu-id="251a8-140">L'abilitazione degli IDN comporta la conversione di tutte le etichette Unicode in un nome di dominio nei rispettivi equivalenti Punycode.</span><span class="sxs-lookup"><span data-stu-id="251a8-140">Enabling IDN will convert all Unicode labels in a domain name to their Punycode equivalents.</span></span> <span data-ttu-id="251a8-141">I nomi Punycode contengono solo caratteri ASCII e iniziano sempre con il prefisso "xn--".</span><span class="sxs-lookup"><span data-stu-id="251a8-141">Punycode names contain only ASCII characters and always start with the xn-- prefix.</span></span> <span data-ttu-id="251a8-142">Questo avviene per supportare i server DNS esistenti in Internet, in quanto la maggior parte dei server DNS supporta solo caratteri ASCII. Vedere il documento RFC 3940.</span><span class="sxs-lookup"><span data-stu-id="251a8-142">The reason for this is to support existing DNS servers on the Internet, since most DNS servers only support ASCII characters (see RFC 3940).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="251a8-143">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="251a8-143">Configuration Files</span></span>  
 <span data-ttu-id="251a8-144">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="251a8-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="251a8-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="251a8-145">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="251a8-146">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="251a8-146">Description</span></span>  
 <span data-ttu-id="251a8-147">Nell'esempio seguente viene illustrata una configurazione utilizzata <xref:System.Uri> dalla classe per supportare l'analisi IRI e i nomi IDN.</span><span class="sxs-lookup"><span data-stu-id="251a8-147">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="251a8-148">Codice</span><span class="sxs-lookup"><span data-stu-id="251a8-148">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="251a8-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="251a8-149">See also</span></span>

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="251a8-150">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="251a8-150">Network Settings Schema</span></span>](index.md)
