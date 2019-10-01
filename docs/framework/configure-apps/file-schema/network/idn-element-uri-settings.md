---
title: Elemento <idn> (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
ms.openlocfilehash: 533b2562f6e5c8d6c2bf452e56dff9a8bf8ab376
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698169"
---
# <a name="idn-element-uri-settings"></a><span data-ttu-id="ebf72-102">Elemento > \<idn (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="ebf72-102">\<idn> Element (Uri Settings)</span></span>

<span data-ttu-id="ebf72-103">Specifica se l'analisi del nome di dominio internazionale (IDN) viene applicata a un nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="ebf72-103">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name.</span></span>
  
[<span data-ttu-id="ebf72-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="ebf72-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="ebf72-105">&nbsp; @ no__t-1[ **\<uri >** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="ebf72-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="ebf72-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<idn >**</span><span class="sxs-lookup"><span data-stu-id="ebf72-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<idn>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebf72-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ebf72-107">Syntax</span></span>  
  
```xml
<idn
  enabled="All|AllExceptIntranet|None"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ebf72-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ebf72-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ebf72-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ebf72-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ebf72-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="ebf72-110">Attributes</span></span>  

|<span data-ttu-id="ebf72-111">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="ebf72-111">**Element**</span></span>|<span data-ttu-id="ebf72-112">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ebf72-112">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="ebf72-113">Specifica se l'analisi del nome di dominio internazionale (IDN) viene applicata a un nome di dominio. il valore predefinito è None.</span><span class="sxs-lookup"><span data-stu-id="ebf72-113">Specifies if Internationalized Domain Name (IDN) parsing is applied to a domain name The default value is none.</span></span>|  

### <a name="child-elements"></a><span data-ttu-id="ebf72-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ebf72-114">Child elements</span></span>

<span data-ttu-id="ebf72-115">nessuno</span><span class="sxs-lookup"><span data-stu-id="ebf72-115">None</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="ebf72-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ebf72-116">Parent elements</span></span>

|<span data-ttu-id="ebf72-117">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="ebf72-117">**Element**</span></span>|<span data-ttu-id="ebf72-118">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ebf72-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ebf72-119">uri</span><span class="sxs-lookup"><span data-stu-id="ebf72-119">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="ebf72-120">Contiene le impostazioni che specificano il modo in cui il .NET Framework gestisce gli indirizzi Web espressi tramite URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="ebf72-120">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  

## <a name="remarks"></a><span data-ttu-id="ebf72-121">Note</span><span class="sxs-lookup"><span data-stu-id="ebf72-121">Remarks</span></span>

<span data-ttu-id="ebf72-122">La classe <xref:System.Uri> esistente è stata estesa in .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="ebf72-122">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="ebf72-123">3,0 SP1 e 2,0 SP1 con supporto per gli identificatori di risorse internazionali (IRI) e i nomi di dominio internazionali (IDN).</span><span class="sxs-lookup"><span data-stu-id="ebf72-123">3.0 SP1, and 2.0 SP1 with support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="ebf72-124">Gli utenti correnti non vedranno alcuna modifica rispetto al comportamento di .NET Framework 2,0, a meno che non vengano specificamente abilitati il supporto di IRI e IDN.</span><span class="sxs-lookup"><span data-stu-id="ebf72-124">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="ebf72-125">Questo garantisce la compatibilità delle applicazioni con le versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ebf72-125">This ensures application compatibility with prior versions of the .NET Framework.</span></span>

<span data-ttu-id="ebf72-126">Per abilitare il supporto per IRI, sono necessarie le due modifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="ebf72-126">To enable support for IRI, the following two changes are required:</span></span>

1. <span data-ttu-id="ebf72-127">Aggiungere la riga seguente al file Machine. config nella directory .NET Framework 2,0:</span><span class="sxs-lookup"><span data-stu-id="ebf72-127">Add the following line to the machine.config file under the .NET Framework 2.0 directory:</span></span>
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="ebf72-128">Specificare se si desidera che l'analisi del nome di dominio internazionalizzazione (IDN) venga applicata al nome di dominio e se devono essere applicate le regole di analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="ebf72-128">Specify whether you want Internationalized Domain Name (IDN) parsing applied to the domain name and whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="ebf72-129">A questo scopo, è possibile usare il file machine.config o il file app.config.</span><span class="sxs-lookup"><span data-stu-id="ebf72-129">This can be done in the machine.config or in the app.config file.</span></span>

 <span data-ttu-id="ebf72-130">Esistono tre possibili valori per IDN a seconda dei server DNS utilizzati:</span><span class="sxs-lookup"><span data-stu-id="ebf72-130">There are three possible values for IDN depending on the DNS servers that are used:</span></span>

- <span data-ttu-id="ebf72-131">IDN abilitato = tutti</span><span class="sxs-lookup"><span data-stu-id="ebf72-131">idn enabled = All</span></span>  

     <span data-ttu-id="ebf72-132">Questo valore convertirà i nomi di dominio Unicode negli equivalenti Punycode (nomi IDN).</span><span class="sxs-lookup"><span data-stu-id="ebf72-132">This value will convert any Unicode domain names to their Punycode equivalents (IDN names).</span></span>

- <span data-ttu-id="ebf72-133">IDN abilitato = AllExceptIntranet</span><span class="sxs-lookup"><span data-stu-id="ebf72-133">idn enabled = AllExceptIntranet</span></span>

     <span data-ttu-id="ebf72-134">Questo valore convertirà tutti i nomi di dominio Unicode non presenti nella rete Intranet locale per utilizzare gli equivalenti Punycode (nomi IDN).</span><span class="sxs-lookup"><span data-stu-id="ebf72-134">This value will convert all Unicode domain names not on the local Intranet to use the Punycode equivalents (IDN names).</span></span> <span data-ttu-id="ebf72-135">In questo caso, per gestire i nomi internazionali sulla Intranet locale, i server DNS utilizzati per la Intranet devono supportare la risoluzione dei nomi Unicode.</span><span class="sxs-lookup"><span data-stu-id="ebf72-135">In this case to handle international names on the local Intranet, the DNS servers that are used for the Intranet should support Unicode name resolution.</span></span>

- <span data-ttu-id="ebf72-136">IDN abilitato = None</span><span class="sxs-lookup"><span data-stu-id="ebf72-136">idn enabled = None</span></span>

     <span data-ttu-id="ebf72-137">Con questo valore non verrà convertito alcun nome di dominio Unicode per l'utilizzo di Punycode.</span><span class="sxs-lookup"><span data-stu-id="ebf72-137">This value will not convert any Unicode domain names to use Punycode.</span></span> <span data-ttu-id="ebf72-138">Si tratta del valore predefinito, coerente con il comportamento .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="ebf72-138">This is the default value which is consistent with the .NET Framework 2.0 behavior.</span></span>

 <span data-ttu-id="ebf72-139">L'abilitazione degli IDN comporta la conversione di tutte le etichette Unicode in un nome di dominio nei rispettivi equivalenti Punycode.</span><span class="sxs-lookup"><span data-stu-id="ebf72-139">Enabling IDN will convert all Unicode labels in a domain name to their Punycode equivalents.</span></span> <span data-ttu-id="ebf72-140">I nomi Punycode contengono solo caratteri ASCII e iniziano sempre con il prefisso "xn--".</span><span class="sxs-lookup"><span data-stu-id="ebf72-140">Punycode names contain only ASCII characters and always start with the xn-- prefix.</span></span> <span data-ttu-id="ebf72-141">Questo avviene per supportare i server DNS esistenti in Internet, in quanto la maggior parte dei server DNS supporta solo caratteri ASCII. Vedere il documento RFC 3940.</span><span class="sxs-lookup"><span data-stu-id="ebf72-141">The reason for this is to support existing DNS servers on the Internet, since most DNS servers only support ASCII characters (see RFC 3940).</span></span>

### <a name="configuration-files"></a><span data-ttu-id="ebf72-142">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="ebf72-142">Configuration files</span></span>

<span data-ttu-id="ebf72-143">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="ebf72-143">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>

## <a name="example"></a><span data-ttu-id="ebf72-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="ebf72-144">Example</span></span>

<span data-ttu-id="ebf72-145">Nell'esempio seguente viene illustrata una configurazione utilizzata dalla classe <xref:System.Uri> per supportare l'analisi IRI e i nomi IDN:</span><span class="sxs-lookup"><span data-stu-id="ebf72-145">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names:</span></span>

```xml
<configuration>
  <uri>
    <idn enabled="All" />
    <iriParsing enabled="true" />
  </uri>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="ebf72-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ebf72-146">See also</span></span>

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="ebf72-147">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="ebf72-147">Network Settings Schema</span></span>](index.md)
