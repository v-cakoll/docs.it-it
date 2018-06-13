---
title: '&lt;UseRandomizedStringHashAlgorithm&gt; elemento'
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
ms.openlocfilehash: a515c3011905c4f5c18ed9d3e8edf489428c04d8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746085"
---
# <a name="ltuserandomizedstringhashalgorithmgt-element"></a><span data-ttu-id="dd549-102">&lt;UseRandomizedStringHashAlgorithm&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="dd549-102">&lt;UseRandomizedStringHashAlgorithm&gt; Element</span></span>
<span data-ttu-id="dd549-103">Determina se common language runtime calcola il codice hash per le stringhe in una base di un dominio di applicazione.</span><span class="sxs-lookup"><span data-stu-id="dd549-103">Determines whether the common language runtime calculates hash codes for strings on a per application domain basis.</span></span>  
  
 <span data-ttu-id="dd549-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="dd549-104">\<configuration></span></span>  
<span data-ttu-id="dd549-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="dd549-105">\<runtime></span></span>  
<span data-ttu-id="dd549-106">\<UseRandomizedStringHashAlgorithm ></span><span class="sxs-lookup"><span data-stu-id="dd549-106">\<UseRandomizedStringHashAlgorithm></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd549-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd549-107">Syntax</span></span>  
  
```xml  
<UseRandomizedStringHashAlgorithm   
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd549-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dd549-108">Attributes and Elements</span></span>  
 <span data-ttu-id="dd549-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dd549-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd549-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="dd549-110">Attributes</span></span>  
  
|<span data-ttu-id="dd549-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="dd549-111">Attribute</span></span>|<span data-ttu-id="dd549-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd549-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="dd549-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="dd549-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="dd549-114">Specifica se i codici hash per le stringhe vengono calcolati in una base di un dominio di applicazione.</span><span class="sxs-lookup"><span data-stu-id="dd549-114">Specifies whether hash codes for strings are calculated on a per application domain basis.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="dd549-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="dd549-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="dd549-116">Valore</span><span class="sxs-lookup"><span data-stu-id="dd549-116">Value</span></span>|<span data-ttu-id="dd549-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd549-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="dd549-118">Common language runtime non calcolare i codici hash per le stringhe in una per ogni singolo dominio di applicazione; un solo algoritmo viene utilizzato per calcolare i codici hash di stringa.</span><span class="sxs-lookup"><span data-stu-id="dd549-118">The common language runtime does not compute hash codes for strings on a per application domain basis; a single algorithm is used to calculate string hash codes.</span></span> <span data-ttu-id="dd549-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="dd549-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="dd549-120">Common language runtime consente di calcolare i codici hash per le stringhe in una base di un dominio di applicazione.</span><span class="sxs-lookup"><span data-stu-id="dd549-120">The common language runtime computes hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="dd549-121">Stringhe identiche in diversi domini applicazione e in diversi processi avranno i codici hash diverso.</span><span class="sxs-lookup"><span data-stu-id="dd549-121">Identical strings in different application domains and in different processes will have different hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dd549-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dd549-122">Child Elements</span></span>  
 <span data-ttu-id="dd549-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="dd549-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dd549-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dd549-124">Parent Elements</span></span>  
  
|<span data-ttu-id="dd549-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="dd549-125">Element</span></span>|<span data-ttu-id="dd549-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd549-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="dd549-127">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dd549-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="dd549-128">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="dd549-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd549-129">Note</span><span class="sxs-lookup"><span data-stu-id="dd549-129">Remarks</span></span>  
 <span data-ttu-id="dd549-130">Per impostazione predefinita, il <xref:System.StringComparer> classe e <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> metodo utilizza un solo algoritmo hash che genera un codice hash coerente tra domini dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="dd549-130">By default, the <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method use a single hashing algorithm that produces a consistent hash code across application domains.</span></span> <span data-ttu-id="dd549-131">Questo è equivalente all'impostazione di `enabled` attributo del `<UseRandomizedStringHashAlgorithm>` elemento `0`.</span><span class="sxs-lookup"><span data-stu-id="dd549-131">This is equivalent to setting the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `0`.</span></span> <span data-ttu-id="dd549-132">Si tratta dell'algoritmo hash utilizzato nel [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd549-132">This is the hashing algorithm used in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span>  
  
 <span data-ttu-id="dd549-133">Il <xref:System.StringComparer> classe e <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> metodo può anche usare un algoritmo di hash diverso che consente di calcolare i codici hash in una base di un dominio di applicazione.</span><span class="sxs-lookup"><span data-stu-id="dd549-133">The <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method can also use a different hashing algorithm that computes hash codes on a per application domain basis.</span></span> <span data-ttu-id="dd549-134">Di conseguenza, i codici hash per le stringhe equivalente variano tra domini dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="dd549-134">As a result, hash codes for equivalent strings will differ across application domains.</span></span> <span data-ttu-id="dd549-135">È una funzionalità che prevede il consenso esplicito; Per sfruttare i vantaggi di esso, è necessario impostare il `enabled` attributo del `<UseRandomizedStringHashAlgorithm>` elemento `1`.</span><span class="sxs-lookup"><span data-stu-id="dd549-135">This is an opt-in feature; to take advantage of it, you must set the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `1`.</span></span>  
  
 <span data-ttu-id="dd549-136">La ricerca della stringa in una tabella hash è in genere un'operazione o (1).</span><span class="sxs-lookup"><span data-stu-id="dd549-136">The string lookup in a hash table is typically an O(1) operation.</span></span> <span data-ttu-id="dd549-137">Tuttavia, quando si verifica un numero elevato di conflitti, la ricerca può diventare un'operazione O (n<sup>2</sup>) operazione.</span><span class="sxs-lookup"><span data-stu-id="dd549-137">However, when a large number of collisions occur, the lookup can become an O(n<sup>2</sup>) operation.</span></span> <span data-ttu-id="dd549-138">È possibile utilizzare il `<UseRandomizedStringHashAlgorithm>` elemento di configurazione per generare un algoritmo di hash caso per ogni dominio applicazione, che a sua volta limita il numero di potenziali conflitti, in particolare quando le chiavi da cui vengono calcolati i codici hash sono basate su dati di input da parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="dd549-138">You can use the `<UseRandomizedStringHashAlgorithm>` configuration element to generate a random hashing algorithm per application domain, which in turn limits the number of potential collisions, particularly when the keys from which the hash codes are calculated are based on data input by users.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd549-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="dd549-139">Example</span></span>  
 <span data-ttu-id="dd549-140">L'esempio seguente definisce un `DisplayString` classe che include una costante di stringa privata, `s`, il cui valore è "This is a una stringa".</span><span class="sxs-lookup"><span data-stu-id="dd549-140">The following example defines a `DisplayString` class that includes a private string constant, `s`, whose value is "This is a string."</span></span> <span data-ttu-id="dd549-141">Include inoltre un `ShowStringHashCode` metodo che visualizza il valore di stringa e il codice hash insieme al nome del dominio dell'applicazione in cui l'esecuzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="dd549-141">It also includes a `ShowStringHashCode` method that displays the string value and its hash code along with the name of the application domain in which the method is executing.</span></span>  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 <span data-ttu-id="dd549-142">Quando si esegue l'esempio senza fornire un file di configurazione, viene visualizzato l'output simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="dd549-142">When you run the example without supplying a configuration file, it displays output similar to the following.</span></span> <span data-ttu-id="dd549-143">Si noti che i codici hash per la stringa siano identici in due domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="dd549-143">Note that the hash codes for the string are identical in the two application domains.</span></span>  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 <span data-ttu-id="dd549-144">Tuttavia, se si aggiunge il file di configurazione seguente alla directory dell'esempio e quindi eseguire l'esempio, i codici hash per la stessa stringa diverso dal dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="dd549-144">However, if you add the following configuration file to the example's directory and then run the example, the hash codes for the same string will differ by application domain.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="dd549-145">Quando il file di configurazione è presente, nell'esempio viene visualizzato il seguente output:</span><span class="sxs-lookup"><span data-stu-id="dd549-145">When the configuration file is present, the example displays the following output:</span></span>  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a><span data-ttu-id="dd549-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd549-146">See Also</span></span>  
 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>  
 <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>  
 <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
