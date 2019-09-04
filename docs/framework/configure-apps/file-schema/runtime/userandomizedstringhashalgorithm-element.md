---
title: <UseRandomizedStringHashAlgorithm> Elemento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UseRandomizedStringHashAlgorithm element
- <UseRandomizedStringHashAlgorithm> element
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49b53dcd4db7e0ac1e9079e763b8ed76c1088e0e
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252192"
---
# <a name="userandomizedstringhashalgorithm-element"></a><span data-ttu-id="3cdfa-102">\<Elemento > UseRandomizedStringHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="3cdfa-102">\<UseRandomizedStringHashAlgorithm> Element</span></span>
<span data-ttu-id="3cdfa-103">Determina se il Common Language Runtime calcola i codici hash per le stringhe in base al dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3cdfa-103">Determines whether the common language runtime calculates hash codes for strings on a per application domain basis.</span></span>  
  
<span data-ttu-id="3cdfa-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3cdfa-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3cdfa-105">&nbsp;&nbsp;[ **\<> di runtime**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="3cdfa-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="3cdfa-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<UseRandomizedStringHashAlgorithm>**</span><span class="sxs-lookup"><span data-stu-id="3cdfa-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<UseRandomizedStringHashAlgorithm>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cdfa-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3cdfa-107">Syntax</span></span>  
  
```xml  
<UseRandomizedStringHashAlgorithm   
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3cdfa-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3cdfa-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3cdfa-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3cdfa-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3cdfa-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="3cdfa-110">Attributes</span></span>  
  
|<span data-ttu-id="3cdfa-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="3cdfa-111">Attribute</span></span>|<span data-ttu-id="3cdfa-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3cdfa-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="3cdfa-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3cdfa-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="3cdfa-114">Specifica se i codici hash per le stringhe vengono calcolati in base al dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3cdfa-114">Specifies whether hash codes for strings are calculated on a per application domain basis.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="3cdfa-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="3cdfa-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="3cdfa-116">Valore</span><span class="sxs-lookup"><span data-stu-id="3cdfa-116">Value</span></span>|<span data-ttu-id="3cdfa-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3cdfa-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="3cdfa-118">Il Common Language Runtime non calcola i codici hash per le stringhe in base al dominio dell'applicazione. viene utilizzato un singolo algoritmo per calcolare i codici hash della stringa.</span><span class="sxs-lookup"><span data-stu-id="3cdfa-118">The common language runtime does not compute hash codes for strings on a per application domain basis; a single algorithm is used to calculate string hash codes.</span></span> <span data-ttu-id="3cdfa-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3cdfa-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="3cdfa-120">Il Common Language Runtime calcola i codici hash per le stringhe in base al dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3cdfa-120">The common language runtime computes hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="3cdfa-121">Stringhe identiche in domini applicazione diversi e in processi diversi avranno codici hash diversi.</span><span class="sxs-lookup"><span data-stu-id="3cdfa-121">Identical strings in different application domains and in different processes will have different hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3cdfa-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3cdfa-122">Child Elements</span></span>  
 <span data-ttu-id="3cdfa-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3cdfa-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3cdfa-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3cdfa-124">Parent Elements</span></span>  
  
|<span data-ttu-id="3cdfa-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="3cdfa-125">Element</span></span>|<span data-ttu-id="3cdfa-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3cdfa-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3cdfa-127">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3cdfa-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3cdfa-128">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3cdfa-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cdfa-129">Note</span><span class="sxs-lookup"><span data-stu-id="3cdfa-129">Remarks</span></span>  
 <span data-ttu-id="3cdfa-130">Per impostazione predefinita, <xref:System.StringComparer> la classe e <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> il metodo usano un unico algoritmo di hashing che produce un codice hash coerente tra i domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="3cdfa-130">By default, the <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method use a single hashing algorithm that produces a consistent hash code across application domains.</span></span> <span data-ttu-id="3cdfa-131">Equivale a impostare l' `enabled` attributo `<UseRandomizedStringHashAlgorithm>` dell'elemento su `0`.</span><span class="sxs-lookup"><span data-stu-id="3cdfa-131">This is equivalent to setting the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `0`.</span></span> <span data-ttu-id="3cdfa-132">Si tratta dell'algoritmo hash utilizzato nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3cdfa-132">This is the hashing algorithm used in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="3cdfa-133">La <xref:System.StringComparer> classe e il <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> metodo possono anche usare un algoritmo di hash diverso che calcola i codici hash in base al dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3cdfa-133">The <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method can also use a different hashing algorithm that computes hash codes on a per application domain basis.</span></span> <span data-ttu-id="3cdfa-134">Di conseguenza, i codici hash per le stringhe equivalenti si differenziano tra domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="3cdfa-134">As a result, hash codes for equivalent strings will differ across application domains.</span></span> <span data-ttu-id="3cdfa-135">Si tratta di una funzionalità di consenso esplicito; per sfruttarlo, è necessario impostare l' `enabled` attributo `<UseRandomizedStringHashAlgorithm>` dell'elemento su `1`.</span><span class="sxs-lookup"><span data-stu-id="3cdfa-135">This is an opt-in feature; to take advantage of it, you must set the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `1`.</span></span>  
  
 <span data-ttu-id="3cdfa-136">La ricerca di stringhe in una tabella hash è in genere un'operazione O (1).</span><span class="sxs-lookup"><span data-stu-id="3cdfa-136">The string lookup in a hash table is typically an O(1) operation.</span></span> <span data-ttu-id="3cdfa-137">Tuttavia, quando si verifica un numero elevato di conflitti, la ricerca può diventare un'operazione O (n<sup>2</sup>).</span><span class="sxs-lookup"><span data-stu-id="3cdfa-137">However, when a large number of collisions occur, the lookup can become an O(n<sup>2</sup>) operation.</span></span> <span data-ttu-id="3cdfa-138">È possibile usare l' `<UseRandomizedStringHashAlgorithm>` elemento di configurazione per generare un algoritmo di hashing casuale per ogni dominio dell'applicazione, che a sua volta limita il numero di potenziali collisioni, in particolare quando le chiavi da cui vengono calcolati i codici hash sono basate sull'input dei dati dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="3cdfa-138">You can use the `<UseRandomizedStringHashAlgorithm>` configuration element to generate a random hashing algorithm per application domain, which in turn limits the number of potential collisions, particularly when the keys from which the hash codes are calculated are based on data input by users.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cdfa-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="3cdfa-139">Example</span></span>  
 <span data-ttu-id="3cdfa-140">Nell'esempio seguente viene definita `DisplayString` una classe che include una costante di stringa `s`privata,, il cui valore è "This is a String".</span><span class="sxs-lookup"><span data-stu-id="3cdfa-140">The following example defines a `DisplayString` class that includes a private string constant, `s`, whose value is "This is a string."</span></span> <span data-ttu-id="3cdfa-141">Include anche un `ShowStringHashCode` metodo che Visualizza il valore stringa e il relativo codice hash insieme al nome del dominio dell'applicazione in cui è in esecuzione il metodo.</span><span class="sxs-lookup"><span data-stu-id="3cdfa-141">It also includes a `ShowStringHashCode` method that displays the string value and its hash code along with the name of the application domain in which the method is executing.</span></span>  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 <span data-ttu-id="3cdfa-142">Quando si esegue l'esempio senza fornire un file di configurazione, viene visualizzato un output simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="3cdfa-142">When you run the example without supplying a configuration file, it displays output similar to the following.</span></span> <span data-ttu-id="3cdfa-143">Si noti che i codici hash per la stringa sono identici nei due domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="3cdfa-143">Note that the hash codes for the string are identical in the two application domains.</span></span>  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 <span data-ttu-id="3cdfa-144">Tuttavia, se si aggiunge il file di configurazione seguente alla directory dell'esempio e quindi si esegue l'esempio, i codici hash per la stessa stringa variano in base al dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3cdfa-144">However, if you add the following configuration file to the example's directory and then run the example, the hash codes for the same string will differ by application domain.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="3cdfa-145">Quando il file di configurazione è presente, nell'esempio viene visualizzato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="3cdfa-145">When the configuration file is present, the example displays the following output:</span></span>  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a><span data-ttu-id="3cdfa-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3cdfa-146">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
