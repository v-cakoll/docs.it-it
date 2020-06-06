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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153777"
---
# <a name="userandomizedstringhashalgorithm-element"></a><span data-ttu-id="fcc53-102">\<UseRandomizedStringHashAlgorithm> Elemento</span><span class="sxs-lookup"><span data-stu-id="fcc53-102">\<UseRandomizedStringHashAlgorithm> Element</span></span>
<span data-ttu-id="fcc53-103">Determina se il Common Language Runtime calcola i codici hash per le stringhe in base al dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fcc53-103">Determines whether the common language runtime calculates hash codes for strings on a per application domain basis.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<UseRandomizedStringHashAlgorithm>**  
  
## <a name="syntax"></a><span data-ttu-id="fcc53-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fcc53-104">Syntax</span></span>  
  
```xml  
<UseRandomizedStringHashAlgorithm
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fcc53-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fcc53-105">Attributes and Elements</span></span>  
 <span data-ttu-id="fcc53-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fcc53-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fcc53-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="fcc53-107">Attributes</span></span>  
  
|<span data-ttu-id="fcc53-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="fcc53-108">Attribute</span></span>|<span data-ttu-id="fcc53-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fcc53-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="fcc53-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fcc53-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="fcc53-111">Specifica se i codici hash per le stringhe vengono calcolati in base al dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fcc53-111">Specifies whether hash codes for strings are calculated on a per application domain basis.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="fcc53-112">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="fcc53-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="fcc53-113">Valore</span><span class="sxs-lookup"><span data-stu-id="fcc53-113">Value</span></span>|<span data-ttu-id="fcc53-114">Description</span><span class="sxs-lookup"><span data-stu-id="fcc53-114">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="fcc53-115">Il Common Language Runtime non calcola i codici hash per le stringhe in base al dominio dell'applicazione. viene utilizzato un singolo algoritmo per calcolare i codici hash della stringa.</span><span class="sxs-lookup"><span data-stu-id="fcc53-115">The common language runtime does not compute hash codes for strings on a per application domain basis; a single algorithm is used to calculate string hash codes.</span></span> <span data-ttu-id="fcc53-116">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="fcc53-116">This is the default.</span></span>|  
|`1`|<span data-ttu-id="fcc53-117">Il Common Language Runtime calcola i codici hash per le stringhe in base al dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fcc53-117">The common language runtime computes hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="fcc53-118">Stringhe identiche in domini applicazione diversi e in processi diversi avranno codici hash diversi.</span><span class="sxs-lookup"><span data-stu-id="fcc53-118">Identical strings in different application domains and in different processes will have different hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fcc53-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fcc53-119">Child Elements</span></span>  
 <span data-ttu-id="fcc53-120">No.</span><span class="sxs-lookup"><span data-stu-id="fcc53-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fcc53-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fcc53-121">Parent Elements</span></span>  
  
|<span data-ttu-id="fcc53-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="fcc53-122">Element</span></span>|<span data-ttu-id="fcc53-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fcc53-123">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fcc53-124">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fcc53-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="fcc53-125">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fcc53-125">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fcc53-126">Commenti</span><span class="sxs-lookup"><span data-stu-id="fcc53-126">Remarks</span></span>  
 <span data-ttu-id="fcc53-127">Per impostazione predefinita, la <xref:System.StringComparer> classe e il <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> Metodo usano un unico algoritmo di hashing che produce un codice hash coerente tra i domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="fcc53-127">By default, the <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method use a single hashing algorithm that produces a consistent hash code across application domains.</span></span> <span data-ttu-id="fcc53-128">Equivale a impostare l' `enabled` attributo dell' `<UseRandomizedStringHashAlgorithm>` elemento su `0` .</span><span class="sxs-lookup"><span data-stu-id="fcc53-128">This is equivalent to setting the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `0`.</span></span> <span data-ttu-id="fcc53-129">Si tratta dell'algoritmo hash utilizzato nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="fcc53-129">This is the hashing algorithm used in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="fcc53-130">La <xref:System.StringComparer> classe e il <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> metodo possono anche usare un algoritmo di hash diverso che calcola i codici hash in base al dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fcc53-130">The <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method can also use a different hashing algorithm that computes hash codes on a per application domain basis.</span></span> <span data-ttu-id="fcc53-131">Di conseguenza, i codici hash per le stringhe equivalenti si differenziano tra domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="fcc53-131">As a result, hash codes for equivalent strings will differ across application domains.</span></span> <span data-ttu-id="fcc53-132">Si tratta di una funzionalità di consenso esplicito; per sfruttarlo, è necessario impostare l' `enabled` attributo dell' `<UseRandomizedStringHashAlgorithm>` elemento su `1` .</span><span class="sxs-lookup"><span data-stu-id="fcc53-132">This is an opt-in feature; to take advantage of it, you must set the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `1`.</span></span>  
  
 <span data-ttu-id="fcc53-133">La ricerca di stringhe in una tabella hash è in genere un'operazione O (1).</span><span class="sxs-lookup"><span data-stu-id="fcc53-133">The string lookup in a hash table is typically an O(1) operation.</span></span> <span data-ttu-id="fcc53-134">Tuttavia, quando si verifica un numero elevato di conflitti, la ricerca può diventare un'operazione O (n<sup>2</sup>).</span><span class="sxs-lookup"><span data-stu-id="fcc53-134">However, when a large number of collisions occur, the lookup can become an O(n<sup>2</sup>) operation.</span></span> <span data-ttu-id="fcc53-135">È possibile usare l' `<UseRandomizedStringHashAlgorithm>` elemento di configurazione per generare un algoritmo di hashing casuale per ogni dominio dell'applicazione, che a sua volta limita il numero di potenziali collisioni, in particolare quando le chiavi da cui vengono calcolati i codici hash sono basate sull'input dei dati da parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="fcc53-135">You can use the `<UseRandomizedStringHashAlgorithm>` configuration element to generate a random hashing algorithm per application domain, which in turn limits the number of potential collisions, particularly when the keys from which the hash codes are calculated are based on data input by users.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcc53-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="fcc53-136">Example</span></span>  
 <span data-ttu-id="fcc53-137">Nell'esempio seguente viene definita una `DisplayString` classe che include una costante di stringa privata, `s` , il cui valore è "This is a String".</span><span class="sxs-lookup"><span data-stu-id="fcc53-137">The following example defines a `DisplayString` class that includes a private string constant, `s`, whose value is "This is a string."</span></span> <span data-ttu-id="fcc53-138">Viene inoltre incluso un metodo `ShowStringHashCode` tramite cui vengono visualizzati il valore stringa e il codice hash con il nome del dominio applicazione in cui il metodo è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fcc53-138">It also includes a `ShowStringHashCode` method that displays the string value and its hash code along with the name of the application domain in which the method is executing.</span></span>  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 <span data-ttu-id="fcc53-139">Quando si esegue l'esempio senza fornire un file di configurazione, restituisce un output analogo al seguente.</span><span class="sxs-lookup"><span data-stu-id="fcc53-139">When you run the example without supplying a configuration file, it displays output similar to the following.</span></span> <span data-ttu-id="fcc53-140">Si noti che i codici hash per la stringa sono identici nei due domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="fcc53-140">Note that the hash codes for the string are identical in the two application domains.</span></span>  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 <span data-ttu-id="fcc53-141">Tuttavia, se si aggiunge il file di configurazione seguente alla directory di esempio e, successivamente, si esegue l'esempio, i codici hash per la stessa stringa risulteranno diversi dal dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fcc53-141">However, if you add the following configuration file to the example's directory and then run the example, the hash codes for the same string will differ by application domain.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="fcc53-142">Quando il file di configurazione è presente, l'esempio visualizza il seguente output:</span><span class="sxs-lookup"><span data-stu-id="fcc53-142">When the configuration file is present, the example displays the following output:</span></span>  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a><span data-ttu-id="fcc53-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcc53-143">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
