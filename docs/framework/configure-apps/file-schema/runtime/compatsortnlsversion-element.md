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
ms.openlocfilehash: f670bd2030e914cc4431c3325215428570ad46cf
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55256611"
---
# <a name="compatsortnlsversion-element"></a><span data-ttu-id="fbe14-102">\<CompatSortNLSVersion > elemento</span><span class="sxs-lookup"><span data-stu-id="fbe14-102">\<CompatSortNLSVersion> Element</span></span>
<span data-ttu-id="fbe14-103">Specifica che nel runtime devono essere utilizzati ordinamenti legacy quando si eseguono confronti di stringhe.</span><span class="sxs-lookup"><span data-stu-id="fbe14-103">Specifies that the runtime should use legacy sort orders when performing string comparisons.</span></span>  
  
 <span data-ttu-id="fbe14-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="fbe14-104">\<configuration></span></span>  
<span data-ttu-id="fbe14-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="fbe14-105">\<runtime></span></span>  
<span data-ttu-id="fbe14-106">\<CompatSortNLSVersion > elemento</span><span class="sxs-lookup"><span data-stu-id="fbe14-106">\<CompatSortNLSVersion> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbe14-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fbe14-107">Syntax</span></span>  
  
```xml  
<CompatSortNLSVersion    
   enabled="4096"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fbe14-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fbe14-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fbe14-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fbe14-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fbe14-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="fbe14-110">Attributes</span></span>  
  
|<span data-ttu-id="fbe14-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="fbe14-111">Attribute</span></span>|<span data-ttu-id="fbe14-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fbe14-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="fbe14-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fbe14-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="fbe14-114">Specifica l'ID delle impostazioni locali di cui deve essere utilizzato l'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="fbe14-114">Specifies the locale ID whose sort order is to be used.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="fbe14-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="fbe14-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="fbe14-116">Valore</span><span class="sxs-lookup"><span data-stu-id="fbe14-116">Value</span></span>|<span data-ttu-id="fbe14-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fbe14-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fbe14-118">4096</span><span class="sxs-lookup"><span data-stu-id="fbe14-118">4096</span></span>|<span data-ttu-id="fbe14-119">ID impostazioni locali mediante il quale viene rappresentato un ordinamento alternativo.</span><span class="sxs-lookup"><span data-stu-id="fbe14-119">The locale ID that represents an alternate sort order.</span></span> <span data-ttu-id="fbe14-120">In questo caso, 4096 rappresenta l'ordinamento di [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] e versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="fbe14-120">In this case, 4096 represents the sort order of the [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] and earlier versions.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fbe14-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fbe14-121">Child Elements</span></span>  
 <span data-ttu-id="fbe14-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="fbe14-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fbe14-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fbe14-123">Parent Elements</span></span>  
  
|<span data-ttu-id="fbe14-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="fbe14-124">Element</span></span>|<span data-ttu-id="fbe14-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fbe14-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fbe14-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fbe14-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="fbe14-127">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fbe14-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbe14-128">Note</span><span class="sxs-lookup"><span data-stu-id="fbe14-128">Remarks</span></span>  
 <span data-ttu-id="fbe14-129">Operazioni di maiuscole e minuscole, l'ordinamento e confronto di stringhe eseguita dal <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> classe la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] conformi a standard Unicode 5.1, i risultati dei metodi di confronto di stringa, ad esempio <xref:System.String.Compare%28System.String%2CSystem.String%29?displayProperty=nameWithType> e <xref:System.String.LastIndexOf%28System.String%29?displayProperty=nameWithType> possono differire dalle versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fbe14-129">Because string comparison, sorting, and casing operations performed by the <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> class in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] conform to the Unicode 5.1 standard, the results of string comparison methods such as <xref:System.String.Compare%28System.String%2CSystem.String%29?displayProperty=nameWithType> and <xref:System.String.LastIndexOf%28System.String%29?displayProperty=nameWithType> may differ from previous versions of the .NET Framework.</span></span> <span data-ttu-id="fbe14-130">Se l'applicazione dipende dal comportamento legacy, è possibile ripristinare il confronto di stringhe e le regole di ordinamento utilizzati in [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] e nelle versioni precedenti includendo l'elemento `<CompatSortNLSVersion>` nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fbe14-130">If your application depends on legacy behavior, you can restore the string comparison and sorting rules used in the [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] and earlier versions by including the `<CompatSortNLSVersion>` element in your application's configuration file.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fbe14-131">Per il ripristino del confronto di stringhe legacy e delle regole di ordinamento è necessaria inoltre la disponibilità della libreria di collegamento dinamico sort00001000.dll nel sistema locale.</span><span class="sxs-lookup"><span data-stu-id="fbe14-131">Restoring legacy string comparison and sorting rules also requires the sort00001000.dll dynamic link library to be available on the local system.</span></span>  
  
 <span data-ttu-id="fbe14-132">È inoltre possibile utilizzare l'ordinamento delle stringhe legacy e le regole di confronto in un dominio dell'applicazione specifico passando la stringa "NetFx40_Legacy20SortingBehavior" al metodo <xref:System.AppDomainSetup.SetCompatibilitySwitches%2A> quando si crea il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fbe14-132">You can also use legacy string sorting and comparison rules in a specific application domain by passing the string "NetFx40_Legacy20SortingBehavior" to the <xref:System.AppDomainSetup.SetCompatibilitySwitches%2A> method when you create the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbe14-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="fbe14-133">Example</span></span>  
 <span data-ttu-id="fbe14-134">Nell'esempio seguente viene creata un'istanza di due oggetti <xref:System.String> e viene chiamato il metodo <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> per confrontarle utilizzando le convenzioni delle impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="fbe14-134">The following example instantiates two <xref:System.String> objects and calls the <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> method to compare them by using the conventions of the current culture.</span></span>  
  
 [!code-csharp[String.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/string.breakingchanges/cs/example1.cs#1)]
 [!code-vb[String.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/string.breakingchanges/vb/example1.vb#1)]  
  
 <span data-ttu-id="fbe14-135">Quando si esegue l'esempio in [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], viene visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="fbe14-135">When you run the example on the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], it displays the following output.</span></span>  
  
```  
sta follows a in the sort order.  
```  
  
 <span data-ttu-id="fbe14-136">Si tratta di un output completamente diverso da quello che viene visualizzato quando si esegue l'esempio in [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fbe14-136">This is completely different from the output that is displayed when you run the example on the [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span></span>  
  
```  
sta equals a in the sort order.  
```  
  
 <span data-ttu-id="fbe14-137">Tuttavia, se si aggiunge il file di configurazione seguente alla directory dell'esempio e successivamente si esegue l'esempio in [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], l'output è identico a quello prodotto dall'esempio quando viene eseguito in [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fbe14-137">However, if you add the following configuration file to the example's directory and then run the example on the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], the output is identical to that produced by the example when it is run on the [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <CompatSortNLSVersion enabled="4096"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fbe14-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbe14-138">See also</span></span>
- [<span data-ttu-id="fbe14-139">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="fbe14-139">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="fbe14-140">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="fbe14-140">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
