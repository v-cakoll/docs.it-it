---
title: '&lt;supportPortability&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 52ef9cce9ee28c6329f688bb9ac751f0f9016657
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="ltsupportportabilitygt-element"></a><span data-ttu-id="7a054-102">&lt;supportPortability&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="7a054-102">&lt;supportPortability&gt; Element</span></span>
<span data-ttu-id="7a054-103">Specifica che un'applicazione può fare riferimento allo stesso assembly in due implementazioni diverse di .NET Framework, disabilitando il comportamento predefinito che tratta gli assembly come equivalenti per scopi di portabilità dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7a054-103">Specifies that an application can reference the same assembly in two different implementations of the .NET Framework, by disabling the default behavior that treats the assemblies as equivalent for application portability purposes.</span></span>  
  
 <span data-ttu-id="7a054-104">\<configurazione > elemento</span><span class="sxs-lookup"><span data-stu-id="7a054-104">\<configuration> Element</span></span>  
<span data-ttu-id="7a054-105">\<runtime > elemento</span><span class="sxs-lookup"><span data-stu-id="7a054-105">\<runtime> Element</span></span>  
<span data-ttu-id="7a054-106">\<assemblyBinding > elemento</span><span class="sxs-lookup"><span data-stu-id="7a054-106">\<assemblyBinding> Element</span></span>  
<span data-ttu-id="7a054-107">\<supportPortability > elemento</span><span class="sxs-lookup"><span data-stu-id="7a054-107">\<supportPortability> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a054-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7a054-108">Syntax</span></span>  
  
```xml  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7a054-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7a054-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7a054-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7a054-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7a054-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="7a054-111">Attributes</span></span>  
  
|<span data-ttu-id="7a054-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="7a054-112">Attribute</span></span>|<span data-ttu-id="7a054-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a054-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7a054-114">PKT</span><span class="sxs-lookup"><span data-stu-id="7a054-114">PKT</span></span>|<span data-ttu-id="7a054-115">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7a054-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="7a054-116">Specifica il token di chiave pubblica dell'assembly interessato, sotto forma di stringa.</span><span class="sxs-lookup"><span data-stu-id="7a054-116">Specifies the public key token of the affected assembly, as a string.</span></span>|  
|<span data-ttu-id="7a054-117">enabled</span><span class="sxs-lookup"><span data-stu-id="7a054-117">enabled</span></span>|<span data-ttu-id="7a054-118">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7a054-118">Optional attribute.</span></span><br /><br /> <span data-ttu-id="7a054-119">Specifica se deve essere abilitato il supporto per la portabilità tra le implementazioni dell'assembly .NET Framework specificato.</span><span class="sxs-lookup"><span data-stu-id="7a054-119">Specifies whether support for portability between implementations of the specified .NET Framework assembly should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="7a054-120">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="7a054-120">enabled Attribute</span></span>  
  
|<span data-ttu-id="7a054-121">Valore</span><span class="sxs-lookup"><span data-stu-id="7a054-121">Value</span></span>|<span data-ttu-id="7a054-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a054-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7a054-123">true</span><span class="sxs-lookup"><span data-stu-id="7a054-123">true</span></span>|<span data-ttu-id="7a054-124">Abilitare il supporto per la portabilità tra implementazioni dell'assembly .NET Framework specificato.</span><span class="sxs-lookup"><span data-stu-id="7a054-124">Enable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="7a054-125">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7a054-125">This is the default.</span></span>|  
|<span data-ttu-id="7a054-126">False</span><span class="sxs-lookup"><span data-stu-id="7a054-126">false</span></span>|<span data-ttu-id="7a054-127">Disabilitare il supporto per la portabilità tra le implementazioni dell'assembly .NET Framework specificato.</span><span class="sxs-lookup"><span data-stu-id="7a054-127">Disable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="7a054-128">In questo modo l'applicazione di riferimenti a più implementazioni dell'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="7a054-128">This enables the application to have references to multiple implementations of the specified assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7a054-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7a054-129">Child Elements</span></span>  
 <span data-ttu-id="7a054-130">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7a054-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7a054-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7a054-131">Parent Elements</span></span>  
  
|<span data-ttu-id="7a054-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="7a054-132">Element</span></span>|<span data-ttu-id="7a054-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a054-133">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7a054-134">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7a054-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="7a054-135">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="7a054-135">Contains information about assembly binding and garbage collection.</span></span>|  
|`assemblyBinding`|<span data-ttu-id="7a054-136">Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.</span><span class="sxs-lookup"><span data-stu-id="7a054-136">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a054-137">Note</span><span class="sxs-lookup"><span data-stu-id="7a054-137">Remarks</span></span>  
 <span data-ttu-id="7a054-138">A partire dal [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], il supporto viene fornito automaticamente per le applicazioni che è possono utilizzare uno dei due implementazioni di .NET Framework, ad esempio l'implementazione di .NET Framework o .NET Framework per Silverlight.</span><span class="sxs-lookup"><span data-stu-id="7a054-138">Beginning with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], support is automatically provided for applications that can use either of two implementations of the .NET Framework, for example either the .NET Framework implementation or the .NET Framework for Silverlight implementation.</span></span> <span data-ttu-id="7a054-139">Le due implementazioni di un particolare assembly di .NET Framework vengono considerate equivalenti dal gestore di associazione di assembly.</span><span class="sxs-lookup"><span data-stu-id="7a054-139">The two implementations of a particular .NET Framework assembly are seen as equivalent by the assembly binder.</span></span> <span data-ttu-id="7a054-140">In alcuni scenari, questa funzionalità di portabilità dell'applicazione può causare problemi.</span><span class="sxs-lookup"><span data-stu-id="7a054-140">In a few scenarios, this application portability feature causes problems.</span></span> <span data-ttu-id="7a054-141">In tali scenari, il `<supportPortability>` elemento può essere usato per disabilitare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="7a054-141">In those scenarios, the `<supportPortability>` element can be used to disable the feature.</span></span>  
  
 <span data-ttu-id="7a054-142">Uno scenario di questo tipo è un assembly che deve fare riferimento all'implementazione di .NET Framework sia .NET Framework per Silverlight di implementazione di un particolare assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="7a054-142">One such scenario is an assembly that has to reference both the .NET Framework implementation and the .NET Framework for Silverlight implementation of a particular reference assembly.</span></span> <span data-ttu-id="7a054-143">Ad esempio, una finestra di progettazione XAML scritta in Windows Presentation Foundation (WPF) potrebbe essere necessario fare riferimento sia all'implementazione Desktop WPF, per l'interfaccia utente della finestra di progettazione e il subset di WPF incluso nell'implementazione di Silverlight.</span><span class="sxs-lookup"><span data-stu-id="7a054-143">For example, a XAML designer written in Windows Presentation Foundation (WPF) might need to reference both the WPF Desktop implementation, for the designer's user interface, and the subset of WPF that is included in the Silverlight implementation.</span></span> <span data-ttu-id="7a054-144">Per impostazione predefinita, i riferimenti separati provocano un errore del compilatore, poiché l'associazione di assembly considera uguali i due assembly.</span><span class="sxs-lookup"><span data-stu-id="7a054-144">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span> <span data-ttu-id="7a054-145">Questo elemento disabilita il comportamento predefinito e consente la compilazione abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7a054-145">This element disables the default behavior, and allows compilation to succeed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7a054-146">Affinché il compilatore passare le informazioni per la logica di associazione di assembly di common language runtime, è necessario utilizzare il `/appconfig` l'opzione del compilatore per specificare il percorso del file app. config che contiene questo elemento.</span><span class="sxs-lookup"><span data-stu-id="7a054-146">In order for the compiler to pass the information to the common language runtime's assembly-binding logic, you must use the `/appconfig` compiler option to specify the location of the app.config file that contains this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a054-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="7a054-147">Example</span></span>  
 <span data-ttu-id="7a054-148">Nell'esempio seguente consente a un'applicazione di riferimenti all'implementazione di .NET Framework sia .NET Framework per Silverlight di implementazione di un assembly di .NET Framework presente in entrambe le implementazioni.</span><span class="sxs-lookup"><span data-stu-id="7a054-148">The following example enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="7a054-149">Il `/appconfig` opzione del compilatore deve essere usata per specificare il percorso del file app. config.</span><span class="sxs-lookup"><span data-stu-id="7a054-149">The `/appconfig` compiler option must be used to specify the location of this app.config file.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding>  
         <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
         <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7a054-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a054-150">See Also</span></span>  
 [<span data-ttu-id="7a054-151">/appconfig (opzioni del compilatore c#)</span><span class="sxs-lookup"><span data-stu-id="7a054-151">/appconfig (C# Compiler Options)</span></span>](http://msdn.microsoft.com/library/ee523958.aspx)  
 [<span data-ttu-id="7a054-152">Panoramica di unificazione degli Assembly di .NET framework</span><span class="sxs-lookup"><span data-stu-id="7a054-152">.NET Framework Assembly Unification Overview</span></span>](http://msdn.microsoft.com/library/8d8cc65e-031d-463b-bde3-2c6dc2e3bc48)
