---
title: '&lt;IDN&gt; elemento (impostazioni Uri)'
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 17f68fbb92797928be911e530232e8638793687f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltidngt-element-uri-settings"></a><span data-ttu-id="ba293-102">&lt;IDN&gt; elemento (impostazioni Uri)</span><span class="sxs-lookup"><span data-stu-id="ba293-102">&lt;idn&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="ba293-103">Specifica se l'analisi IDN (Internationalized Domain Name) viene applicato a un nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="ba293-103">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="ba293-104">Gerarchia dello schema</span><span class="sxs-lookup"><span data-stu-id="ba293-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="ba293-105">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="ba293-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="ba293-106">\<URI > elemento (impostazioni Uri)</span><span class="sxs-lookup"><span data-stu-id="ba293-106">\<Uri> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [<span data-ttu-id="ba293-107">\<IDN ></span><span class="sxs-lookup"><span data-stu-id="ba293-107">\<idn></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="ba293-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ba293-108">Syntax</span></span>  
  
```xml  
<idn  
  enabled="All|AllExceptIntranet|None"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba293-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ba293-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ba293-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ba293-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba293-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="ba293-111">Attributes</span></span>  
  
|<span data-ttu-id="ba293-112">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="ba293-112">**Element**</span></span>|<span data-ttu-id="ba293-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ba293-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="ba293-114">Specifica che se l'analisi IDN (Internationalized Domain Name) viene applicato a un nome di dominio il valore predefinito è none.</span><span class="sxs-lookup"><span data-stu-id="ba293-114">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name The default value is none.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba293-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ba293-115">Child Elements</span></span>  
 <span data-ttu-id="ba293-116">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ba293-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ba293-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ba293-117">Parent Elements</span></span>  
  
|<span data-ttu-id="ba293-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="ba293-118">**Element**</span></span>|<span data-ttu-id="ba293-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ba293-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ba293-120">URI</span><span class="sxs-lookup"><span data-stu-id="ba293-120">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="ba293-121">Contiene le impostazioni che specificano come .NET Framework gestisce gli indirizzi web espressi tramite uniform resource identifier (URI).</span><span class="sxs-lookup"><span data-stu-id="ba293-121">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba293-122">Note</span><span class="sxs-lookup"><span data-stu-id="ba293-122">Remarks</span></span>  
 <span data-ttu-id="ba293-123">Esistente <xref:System.Uri> classe è stata estesa in .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="ba293-123">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="ba293-124">3.0 SP1 e 2.0 SP1 con supporto per gli identificatori IRI (International Resource) e IDN (Internationalized Domain nomi).</span><span class="sxs-lookup"><span data-stu-id="ba293-124">3.0 SP1, and 2.0 SP1 with support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="ba293-125">Gli utenti non visualizzeranno qualsiasi modifica rispetto al comportamento di .NET Framework 2.0 a meno che non consentono in modo specifico IRI e IDN supportano.</span><span class="sxs-lookup"><span data-stu-id="ba293-125">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="ba293-126">Questo garantisce la compatibilità delle applicazioni con le versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ba293-126">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="ba293-127">Per abilitare il supporto per IRI, sono necessarie le seguenti due modifiche:</span><span class="sxs-lookup"><span data-stu-id="ba293-127">To enable support for IRI, the following two changes are required:</span></span>  
  
1.  <span data-ttu-id="ba293-128">Aggiungere la riga seguente al file Machine. config nella directory di .NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="ba293-128">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  <span data-ttu-id="ba293-129">Specificare se l'analisi IDN (Internationalized Domain Name) applicata al nome di dominio e se devono essere applicate le regole di analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="ba293-129">Specify whether you want Internationalized Domain Name (IDN) parsing applied to the domain name and whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="ba293-130">A questo scopo, è possibile usare il file machine.config o il file app.config.</span><span class="sxs-lookup"><span data-stu-id="ba293-130">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="ba293-131">Esistono tre possibili valori per IDN a seconda di server DNS che vengono utilizzati:</span><span class="sxs-lookup"><span data-stu-id="ba293-131">There are three possible values for IDN depending on the DNS servers that are used:</span></span>  
  
-   <span data-ttu-id="ba293-132">IDN abilitata = All</span><span class="sxs-lookup"><span data-stu-id="ba293-132">idn enabled = All</span></span>  
  
     <span data-ttu-id="ba293-133">Questo valore convertirà i nomi di dominio Unicode equivalenti Punycode (nomi IDN).</span><span class="sxs-lookup"><span data-stu-id="ba293-133">This value will convert any Unicode domain names to their Punycode equivalents (IDN names).</span></span>  
  
-   <span data-ttu-id="ba293-134">IDN abilitata = AllExceptIntranet</span><span class="sxs-lookup"><span data-stu-id="ba293-134">idn enabled = AllExceptIntranet</span></span>  
  
     <span data-ttu-id="ba293-135">Questo valore verrà convertito tutti i nomi di dominio Unicode non sulla rete Intranet locale per l'utilizzo degli equivalenti Punycode (nomi IDN).</span><span class="sxs-lookup"><span data-stu-id="ba293-135">This value will convert all Unicode domain names not on the local Intranet to use the Punycode equivalents (IDN names).</span></span> <span data-ttu-id="ba293-136">In questo caso, per gestire nomi internazionali sulla rete Intranet locale, i server DNS utilizzati per la rete Intranet devono supportare la risoluzione dei nomi di Unicode.</span><span class="sxs-lookup"><span data-stu-id="ba293-136">In this case to handle international names on the local Intranet, the DNS servers that are used for the Intranet should support Unicode name resolution.</span></span>  
  
-   <span data-ttu-id="ba293-137">IDN abilitata = nessuno</span><span class="sxs-lookup"><span data-stu-id="ba293-137">idn enabled = None</span></span>  
  
     <span data-ttu-id="ba293-138">Questo valore non convertirà i nomi di dominio Unicode per l'utilizzo di Punycode.</span><span class="sxs-lookup"><span data-stu-id="ba293-138">This value will not convert any Unicode domain names to use Punycode.</span></span> <span data-ttu-id="ba293-139">Questo è il valore predefinito è coerenza con il comportamento di .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="ba293-139">This is the default value which is consistent with the .NET Framework 2.0 behaviour.</span></span>  
  
 <span data-ttu-id="ba293-140">L'abilitazione degli IDN comporta la conversione di tutte le etichette Unicode in un nome di dominio nei rispettivi equivalenti Punycode.</span><span class="sxs-lookup"><span data-stu-id="ba293-140">Enabling IDN will convert all Unicode labels in a domain name to their Punycode equivalents.</span></span> <span data-ttu-id="ba293-141">I nomi Punycode contengono solo caratteri ASCII e iniziano sempre con il prefisso "xn--".</span><span class="sxs-lookup"><span data-stu-id="ba293-141">Punycode names contain only ASCII characters and always start with the xn-- prefix.</span></span> <span data-ttu-id="ba293-142">Questo avviene per supportare i server DNS esistenti in Internet, in quanto la maggior parte dei server DNS supporta solo caratteri ASCII. Vedere il documento RFC 3940.</span><span class="sxs-lookup"><span data-stu-id="ba293-142">The reason for this is to support existing DNS servers on the Internet, since most DNS servers only support ASCII characters (see RFC 3940).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="ba293-143">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="ba293-143">Configuration Files</span></span>  
 <span data-ttu-id="ba293-144">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="ba293-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba293-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="ba293-145">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="ba293-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba293-146">Description</span></span>  
 <span data-ttu-id="ba293-147">Nell'esempio seguente viene mostrata una configurazione utilizzata per la <xref:System.Uri> classe per supportare l'analisi IRI e i nomi IDN.</span><span class="sxs-lookup"><span data-stu-id="ba293-147">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ba293-148">Codice</span><span class="sxs-lookup"><span data-stu-id="ba293-148">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba293-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba293-149">See Also</span></span>  
 <xref:System.Configuration.IdnElement?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 [<span data-ttu-id="ba293-150">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="ba293-150">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
