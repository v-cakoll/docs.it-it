---
title: <CompatSortNLSVersion> Elemento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <CompatSortNLSVersion> element
- CompatSortNLSVersion element
ms.assetid: 782cc82e-83f7-404a-80b7-6d3061a8b6e3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 575d44ad9ecf445ba5d4b7fbe47032127ccb33ae
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252726"
---
# <a name="compatsortnlsversion-element"></a><span data-ttu-id="14764-102">\<Elemento > CompatSortNLSVersion</span><span class="sxs-lookup"><span data-stu-id="14764-102">\<CompatSortNLSVersion> Element</span></span>
<span data-ttu-id="14764-103">Specifica che nel runtime devono essere utilizzati ordinamenti legacy quando si eseguono confronti di stringhe.</span><span class="sxs-lookup"><span data-stu-id="14764-103">Specifies that the runtime should use legacy sort orders when performing string comparisons.</span></span>  
  
<span data-ttu-id="14764-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="14764-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="14764-105">&nbsp;&nbsp;[ **\<> di runtime**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="14764-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="14764-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<CompatSortNLSVersion>**</span><span class="sxs-lookup"><span data-stu-id="14764-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<CompatSortNLSVersion>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14764-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="14764-107">Syntax</span></span>  
  
```xml  
<CompatSortNLSVersion    
   enabled="4096"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14764-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="14764-108">Attributes and Elements</span></span>  
 <span data-ttu-id="14764-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="14764-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14764-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="14764-110">Attributes</span></span>  
  
|<span data-ttu-id="14764-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="14764-111">Attribute</span></span>|<span data-ttu-id="14764-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="14764-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="14764-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="14764-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="14764-114">Specifica l'ID delle impostazioni locali di cui deve essere utilizzato l'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="14764-114">Specifies the locale ID whose sort order is to be used.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="14764-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="14764-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="14764-116">Valore</span><span class="sxs-lookup"><span data-stu-id="14764-116">Value</span></span>|<span data-ttu-id="14764-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="14764-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="14764-118">4096</span><span class="sxs-lookup"><span data-stu-id="14764-118">4096</span></span>|<span data-ttu-id="14764-119">ID impostazioni locali mediante il quale viene rappresentato un ordinamento alternativo.</span><span class="sxs-lookup"><span data-stu-id="14764-119">The locale ID that represents an alternate sort order.</span></span> <span data-ttu-id="14764-120">In questo caso, 4096 rappresenta l'ordinamento di .NET Framework 3,5 e versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="14764-120">In this case, 4096 represents the sort order of the .NET Framework 3.5 and earlier versions.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14764-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="14764-121">Child Elements</span></span>  
 <span data-ttu-id="14764-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="14764-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="14764-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="14764-123">Parent Elements</span></span>  
  
|<span data-ttu-id="14764-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="14764-124">Element</span></span>|<span data-ttu-id="14764-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="14764-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="14764-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="14764-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="14764-127">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="14764-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14764-128">Note</span><span class="sxs-lookup"><span data-stu-id="14764-128">Remarks</span></span>  
 <span data-ttu-id="14764-129">Poiché le operazioni di confronto tra stringhe, ordinamento e maiuscole e <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> minuscole eseguite dalla classe nel .NET Framework 4 sono conformi allo standard Unicode 5,1, i risultati dei <xref:System.String.Compare%28System.String%2CSystem.String%29?displayProperty=nameWithType> metodi <xref:System.String.LastIndexOf%28System.String%29?displayProperty=nameWithType> di confronto tra stringhe quali e possono differire da versioni precedenti del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="14764-129">Because string comparison, sorting, and casing operations performed by the <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> class in the .NET Framework 4 conform to the Unicode 5.1 standard, the results of string comparison methods such as <xref:System.String.Compare%28System.String%2CSystem.String%29?displayProperty=nameWithType> and <xref:System.String.LastIndexOf%28System.String%29?displayProperty=nameWithType> may differ from previous versions of the .NET Framework.</span></span> <span data-ttu-id="14764-130">Se l'applicazione dipende dal comportamento legacy, è possibile ripristinare le regole di ordinamento e confronto delle stringhe utilizzate nel .NET Framework 3,5 e nelle versioni precedenti includendo l' `<CompatSortNLSVersion>` elemento nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="14764-130">If your application depends on legacy behavior, you can restore the string comparison and sorting rules used in the .NET Framework 3.5 and earlier versions by including the `<CompatSortNLSVersion>` element in your application's configuration file.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="14764-131">Per il ripristino del confronto di stringhe legacy e delle regole di ordinamento è necessaria inoltre la disponibilità della libreria di collegamento dinamico sort00001000.dll nel sistema locale.</span><span class="sxs-lookup"><span data-stu-id="14764-131">Restoring legacy string comparison and sorting rules also requires the sort00001000.dll dynamic link library to be available on the local system.</span></span>  
  
 <span data-ttu-id="14764-132">È inoltre possibile utilizzare l'ordinamento delle stringhe legacy e le regole di confronto in un dominio dell'applicazione specifico passando la stringa "NetFx40_Legacy20SortingBehavior" al metodo <xref:System.AppDomainSetup.SetCompatibilitySwitches%2A> quando si crea il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="14764-132">You can also use legacy string sorting and comparison rules in a specific application domain by passing the string "NetFx40_Legacy20SortingBehavior" to the <xref:System.AppDomainSetup.SetCompatibilitySwitches%2A> method when you create the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14764-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="14764-133">Example</span></span>  
 <span data-ttu-id="14764-134">Nell'esempio seguente viene creata un'istanza di due oggetti <xref:System.String> e viene chiamato il metodo <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> per confrontarle utilizzando le convenzioni delle impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="14764-134">The following example instantiates two <xref:System.String> objects and calls the <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> method to compare them by using the conventions of the current culture.</span></span>  
  
 [!code-csharp[String.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/string.breakingchanges/cs/example1.cs#1)]
 [!code-vb[String.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/string.breakingchanges/vb/example1.vb#1)]  
  
 <span data-ttu-id="14764-135">Quando si esegue l'esempio in .NET Framework 4, viene visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="14764-135">When you run the example on the .NET Framework 4, it displays the following output.</span></span>  
  
```  
sta follows a in the sort order.  
```  
  
 <span data-ttu-id="14764-136">Questo è completamente diverso dall'output visualizzato quando si esegue l'esempio in .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="14764-136">This is completely different from the output that is displayed when you run the example on the .NET Framework 3.5.</span></span>  
  
```  
sta equals a in the sort order.  
```  
  
 <span data-ttu-id="14764-137">Tuttavia, se si aggiunge il file di configurazione seguente alla directory dell'esempio e quindi si esegue l'esempio in .NET Framework 4, l'output sarà identico a quello prodotto dall'esempio quando viene eseguito nel .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="14764-137">However, if you add the following configuration file to the example's directory and then run the example on the .NET Framework 4, the output is identical to that produced by the example when it is run on the .NET Framework 3.5.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <CompatSortNLSVersion enabled="4096"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="14764-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14764-138">See also</span></span>

- [<span data-ttu-id="14764-139">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="14764-139">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="14764-140">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="14764-140">Configuration File Schema</span></span>](../index.md)
