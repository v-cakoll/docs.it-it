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
ms.openlocfilehash: a9afa0db516a542b74d08a4c3754a3244abbbea7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153777"
---
# <a name="userandomizedstringhashalgorithm-element"></a><span data-ttu-id="59b1d-102">\<Elemento UseRandomizedStringHashAlgorithm></span><span class="sxs-lookup"><span data-stu-id="59b1d-102">\<UseRandomizedStringHashAlgorithm> Element</span></span>
<span data-ttu-id="59b1d-103">Determina se Common Language Runtime calcola i codici hash per le stringhe in base al dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="59b1d-103">Determines whether the common language runtime calculates hash codes for strings on a per application domain basis.</span></span>  
  
<span data-ttu-id="59b1d-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="59b1d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="59b1d-105">&nbsp;&nbsp;[**\<>di runtime**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="59b1d-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="59b1d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<UseRandomizedStringHashAlgorithm>**</span><span class="sxs-lookup"><span data-stu-id="59b1d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<UseRandomizedStringHashAlgorithm>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59b1d-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="59b1d-107">Syntax</span></span>  
  
```xml  
<UseRandomizedStringHashAlgorithm
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59b1d-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="59b1d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="59b1d-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="59b1d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59b1d-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="59b1d-110">Attributes</span></span>  
  
|<span data-ttu-id="59b1d-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="59b1d-111">Attribute</span></span>|<span data-ttu-id="59b1d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="59b1d-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="59b1d-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="59b1d-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="59b1d-114">Specifica se i codici hash per le stringhe vengono calcolati in base al dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="59b1d-114">Specifies whether hash codes for strings are calculated on a per application domain basis.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="59b1d-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="59b1d-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="59b1d-116">valore</span><span class="sxs-lookup"><span data-stu-id="59b1d-116">Value</span></span>|<span data-ttu-id="59b1d-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="59b1d-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="59b1d-118">Common Language Runtime non calcola i codici hash per le stringhe in base al dominio applicazione. un singolo algoritmo viene utilizzato per calcolare i codici hash delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="59b1d-118">The common language runtime does not compute hash codes for strings on a per application domain basis; a single algorithm is used to calculate string hash codes.</span></span> <span data-ttu-id="59b1d-119">Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="59b1d-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="59b1d-120">Common Language Runtime calcola i codici hash per le stringhe in base al dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="59b1d-120">The common language runtime computes hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="59b1d-121">Stringhe identiche in domini applicazione diversi e in processi diversi avranno codici hash diversi.</span><span class="sxs-lookup"><span data-stu-id="59b1d-121">Identical strings in different application domains and in different processes will have different hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59b1d-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="59b1d-122">Child Elements</span></span>  
 <span data-ttu-id="59b1d-123">No.</span><span class="sxs-lookup"><span data-stu-id="59b1d-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59b1d-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="59b1d-124">Parent Elements</span></span>  
  
|<span data-ttu-id="59b1d-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="59b1d-125">Element</span></span>|<span data-ttu-id="59b1d-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="59b1d-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="59b1d-127">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="59b1d-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="59b1d-128">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="59b1d-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59b1d-129">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="59b1d-129">Remarks</span></span>  
 <span data-ttu-id="59b1d-130">Per impostazione <xref:System.StringComparer> predefinita, <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> la classe e il metodo utilizzano un singolo algoritmo hash che produce un codice hash coerente tra i domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="59b1d-130">By default, the <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method use a single hashing algorithm that produces a consistent hash code across application domains.</span></span> <span data-ttu-id="59b1d-131">Equivale a impostare `enabled` l'attributo dell'elemento `<UseRandomizedStringHashAlgorithm>` su `0`.</span><span class="sxs-lookup"><span data-stu-id="59b1d-131">This is equivalent to setting the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `0`.</span></span> <span data-ttu-id="59b1d-132">Si tratta dell'algoritmo hash utilizzato in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="59b1d-132">This is the hashing algorithm used in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="59b1d-133">La <xref:System.StringComparer> classe <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> e il metodo possono inoltre utilizzare un algoritmo hash diverso che calcola i codici hash in base al dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="59b1d-133">The <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method can also use a different hashing algorithm that computes hash codes on a per application domain basis.</span></span> <span data-ttu-id="59b1d-134">Di conseguenza, i codici hash per le stringhe equivalenti saranno diversi tra i domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="59b1d-134">As a result, hash codes for equivalent strings will differ across application domains.</span></span> <span data-ttu-id="59b1d-135">Questa è una funzione di opt-in; per trarne vantaggio, è `enabled` necessario impostare l'attributo dell'elemento `<UseRandomizedStringHashAlgorithm>` su `1`.</span><span class="sxs-lookup"><span data-stu-id="59b1d-135">This is an opt-in feature; to take advantage of it, you must set the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `1`.</span></span>  
  
 <span data-ttu-id="59b1d-136">La ricerca di stringhe in una tabella hash è in genere un'operazione O(1).</span><span class="sxs-lookup"><span data-stu-id="59b1d-136">The string lookup in a hash table is typically an O(1) operation.</span></span> <span data-ttu-id="59b1d-137">Tuttavia, quando si verifica un numero elevato di conflitti, la ricerca può diventare un'operazione O(n<sup>2</sup>).</span><span class="sxs-lookup"><span data-stu-id="59b1d-137">However, when a large number of collisions occur, the lookup can become an O(n<sup>2</sup>) operation.</span></span> <span data-ttu-id="59b1d-138">È possibile `<UseRandomizedStringHashAlgorithm>` utilizzare l'elemento configuration per generare un algoritmo hash casuale per ogni dominio applicazione, che a sua volta limita il numero di potenziali conflitti, in particolare quando le chiavi da cui vengono calcolati i codici hash sono basate sull'immissione di dati da parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="59b1d-138">You can use the `<UseRandomizedStringHashAlgorithm>` configuration element to generate a random hashing algorithm per application domain, which in turn limits the number of potential collisions, particularly when the keys from which the hash codes are calculated are based on data input by users.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59b1d-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="59b1d-139">Example</span></span>  
 <span data-ttu-id="59b1d-140">Nell'esempio riportato `DisplayString` di seguito viene definita `s`una classe che include una costante di stringa privata, , il cui valore è "This is a string".</span><span class="sxs-lookup"><span data-stu-id="59b1d-140">The following example defines a `DisplayString` class that includes a private string constant, `s`, whose value is "This is a string."</span></span> <span data-ttu-id="59b1d-141">Viene inoltre incluso un metodo `ShowStringHashCode` tramite cui vengono visualizzati il valore stringa e il codice hash con il nome del dominio applicazione in cui il metodo è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="59b1d-141">It also includes a `ShowStringHashCode` method that displays the string value and its hash code along with the name of the application domain in which the method is executing.</span></span>  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 <span data-ttu-id="59b1d-142">Quando si esegue l'esempio senza fornire un file di configurazione, restituisce un output analogo al seguente.</span><span class="sxs-lookup"><span data-stu-id="59b1d-142">When you run the example without supplying a configuration file, it displays output similar to the following.</span></span> <span data-ttu-id="59b1d-143">Si noti che i codici hash per la stringa sono identici nei due domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="59b1d-143">Note that the hash codes for the string are identical in the two application domains.</span></span>  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 <span data-ttu-id="59b1d-144">Tuttavia, se si aggiunge il file di configurazione seguente alla directory di esempio e, successivamente, si esegue l'esempio, i codici hash per la stessa stringa risulteranno diversi dal dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="59b1d-144">However, if you add the following configuration file to the example's directory and then run the example, the hash codes for the same string will differ by application domain.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="59b1d-145">Quando il file di configurazione è presente, l'esempio visualizza il seguente output:</span><span class="sxs-lookup"><span data-stu-id="59b1d-145">When the configuration file is present, the example displays the following output:</span></span>  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a><span data-ttu-id="59b1d-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59b1d-146">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
