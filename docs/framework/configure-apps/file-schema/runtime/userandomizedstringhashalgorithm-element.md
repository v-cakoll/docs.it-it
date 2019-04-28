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
ms.openlocfilehash: 2a51b9fb485da605effbad0e81b8baf5e05e382a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675091"
---
# <a name="userandomizedstringhashalgorithm-element"></a><span data-ttu-id="b7043-102">\<UseRandomizedStringHashAlgorithm > elemento</span><span class="sxs-lookup"><span data-stu-id="b7043-102">\<UseRandomizedStringHashAlgorithm> Element</span></span>
<span data-ttu-id="b7043-103">Determina se common language runtime calcola i codici hash per le stringhe in una base di dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b7043-103">Determines whether the common language runtime calculates hash codes for strings on a per application domain basis.</span></span>  
  
 <span data-ttu-id="b7043-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b7043-104">\<configuration></span></span>  
<span data-ttu-id="b7043-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="b7043-105">\<runtime></span></span>  
<span data-ttu-id="b7043-106">\<UseRandomizedStringHashAlgorithm></span><span class="sxs-lookup"><span data-stu-id="b7043-106">\<UseRandomizedStringHashAlgorithm></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7043-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b7043-107">Syntax</span></span>  
  
```xml  
<UseRandomizedStringHashAlgorithm   
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7043-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b7043-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b7043-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b7043-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7043-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="b7043-110">Attributes</span></span>  
  
|<span data-ttu-id="b7043-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="b7043-111">Attribute</span></span>|<span data-ttu-id="b7043-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b7043-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="b7043-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b7043-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="b7043-114">Specifica se i codici hash per le stringhe vengono calcolati su una base di dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b7043-114">Specifies whether hash codes for strings are calculated on a per application domain basis.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b7043-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="b7043-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="b7043-116">Valore</span><span class="sxs-lookup"><span data-stu-id="b7043-116">Value</span></span>|<span data-ttu-id="b7043-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b7043-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="b7043-118">Common language runtime non calcola i codici hash per le stringhe in una base al dominio applicazione; un singolo algoritmo viene utilizzato per calcolare i codici hash di stringa.</span><span class="sxs-lookup"><span data-stu-id="b7043-118">The common language runtime does not compute hash codes for strings on a per application domain basis; a single algorithm is used to calculate string hash codes.</span></span> <span data-ttu-id="b7043-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b7043-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="b7043-120">Common language runtime calcola i codici hash per le stringhe in una base di dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b7043-120">The common language runtime computes hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="b7043-121">Stringhe identiche in domini applicazione diversi e in processi diversi avranno i codici hash differenti.</span><span class="sxs-lookup"><span data-stu-id="b7043-121">Identical strings in different application domains and in different processes will have different hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7043-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b7043-122">Child Elements</span></span>  
 <span data-ttu-id="b7043-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b7043-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b7043-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b7043-124">Parent Elements</span></span>  
  
|<span data-ttu-id="b7043-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="b7043-125">Element</span></span>|<span data-ttu-id="b7043-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b7043-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b7043-127">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b7043-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b7043-128">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b7043-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7043-129">Note</span><span class="sxs-lookup"><span data-stu-id="b7043-129">Remarks</span></span>  
 <span data-ttu-id="b7043-130">Per impostazione predefinita, il <xref:System.StringComparer> classe e il <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> metodo usare un singolo algoritmo di hash che produce un codice hash coerente tra più domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="b7043-130">By default, the <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method use a single hashing algorithm that produces a consistent hash code across application domains.</span></span> <span data-ttu-id="b7043-131">Ciò equivale a impostare il `enabled` attributo del `<UseRandomizedStringHashAlgorithm>` elemento `0`.</span><span class="sxs-lookup"><span data-stu-id="b7043-131">This is equivalent to setting the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `0`.</span></span> <span data-ttu-id="b7043-132">Questo è l'algoritmo hash usato nel [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7043-132">This is the hashing algorithm used in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span>  
  
 <span data-ttu-id="b7043-133">Il <xref:System.StringComparer> classe e il <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> metodo può anche usare un algoritmo di hash diverso che calcola i codici hash in una base di dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b7043-133">The <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method can also use a different hashing algorithm that computes hash codes on a per application domain basis.</span></span> <span data-ttu-id="b7043-134">Di conseguenza, i codici hash per le stringhe equivalenti risulteranno diversi tra i domini dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b7043-134">As a result, hash codes for equivalent strings will differ across application domains.</span></span> <span data-ttu-id="b7043-135">Si tratta di una funzionalità che prevede il consenso esplicito; Per sfruttare i vantaggi di esso, è necessario impostare il `enabled` attributo del `<UseRandomizedStringHashAlgorithm>` elemento `1`.</span><span class="sxs-lookup"><span data-stu-id="b7043-135">This is an opt-in feature; to take advantage of it, you must set the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `1`.</span></span>  
  
 <span data-ttu-id="b7043-136">La ricerca di stringhe in una tabella hash è in genere un'operazione o (1).</span><span class="sxs-lookup"><span data-stu-id="b7043-136">The string lookup in a hash table is typically an O(1) operation.</span></span> <span data-ttu-id="b7043-137">Tuttavia, quando si verificano numerosi conflitti, la ricerca può diventare un'operazione O (n<sup>2</sup>) operazione.</span><span class="sxs-lookup"><span data-stu-id="b7043-137">However, when a large number of collisions occur, the lookup can become an O(n<sup>2</sup>) operation.</span></span> <span data-ttu-id="b7043-138">È possibile usare il `<UseRandomizedStringHashAlgorithm>` elemento di configurazione per generare un algoritmo di hash casuale per ogni dominio applicazione, che a sua volta limita il numero di potenziali conflitti, in particolare quando le chiavi da cui i codici hash vengono calcolati sono basate su immissione dei dati dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="b7043-138">You can use the `<UseRandomizedStringHashAlgorithm>` configuration element to generate a random hashing algorithm per application domain, which in turn limits the number of potential collisions, particularly when the keys from which the hash codes are calculated are based on data input by users.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7043-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="b7043-139">Example</span></span>  
 <span data-ttu-id="b7043-140">L'esempio seguente definisce una `DisplayString` classe che include una costante di stringa privata, `s`, il cui valore è "This is a una stringa".</span><span class="sxs-lookup"><span data-stu-id="b7043-140">The following example defines a `DisplayString` class that includes a private string constant, `s`, whose value is "This is a string."</span></span> <span data-ttu-id="b7043-141">Include inoltre un `ShowStringHashCode` metodo che consente di visualizzare il valore della stringa e il codice hash con il nome del dominio dell'applicazione in cui l'esecuzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="b7043-141">It also includes a `ShowStringHashCode` method that displays the string value and its hash code along with the name of the application domain in which the method is executing.</span></span>  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 <span data-ttu-id="b7043-142">Quando si esegue l'esempio senza fornire un file di configurazione, viene visualizzato output simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="b7043-142">When you run the example without supplying a configuration file, it displays output similar to the following.</span></span> <span data-ttu-id="b7043-143">Si noti che i codici hash per la stringa sono identici in due domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="b7043-143">Note that the hash codes for the string are identical in the two application domains.</span></span>  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 <span data-ttu-id="b7043-144">Tuttavia, se si aggiunge il file di configurazione seguente alla directory di esempio e quindi eseguire l'esempio, i codici hash per la stessa stringa risulteranno diversi dal dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b7043-144">However, if you add the following configuration file to the example's directory and then run the example, the hash codes for the same string will differ by application domain.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="b7043-145">Quando il file di configurazione è presente, l'esempio visualizza l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="b7043-145">When the configuration file is present, the example displays the following output:</span></span>  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a><span data-ttu-id="b7043-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7043-146">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
