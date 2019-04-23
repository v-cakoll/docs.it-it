---
title: <supportPortability> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cc26f9721e911e05c5b5d4092be21a4e1191c84
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183943"
---
# <a name="supportportability-element"></a><span data-ttu-id="18bd6-102">\<supportPortability > elemento</span><span class="sxs-lookup"><span data-stu-id="18bd6-102">\<supportPortability> Element</span></span>
<span data-ttu-id="18bd6-103">Specifica che un'applicazione può fare riferimento allo stesso assembly in due implementazioni diverse di .NET Framework, disabilitando il comportamento predefinito che tratta gli assembly come equivalenti per scopi di portabilità dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="18bd6-103">Specifies that an application can reference the same assembly in two different implementations of the .NET Framework, by disabling the default behavior that treats the assemblies as equivalent for application portability purposes.</span></span>  
  
 <span data-ttu-id="18bd6-104">\<configurazione > elemento</span><span class="sxs-lookup"><span data-stu-id="18bd6-104">\<configuration> Element</span></span>  
<span data-ttu-id="18bd6-105">\<runtime > elemento</span><span class="sxs-lookup"><span data-stu-id="18bd6-105">\<runtime> Element</span></span>  
<span data-ttu-id="18bd6-106">\<assemblyBinding > elemento</span><span class="sxs-lookup"><span data-stu-id="18bd6-106">\<assemblyBinding> Element</span></span>  
<span data-ttu-id="18bd6-107">\<supportPortability > elemento</span><span class="sxs-lookup"><span data-stu-id="18bd6-107">\<supportPortability> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18bd6-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18bd6-108">Syntax</span></span>  
  
```xml  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18bd6-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="18bd6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="18bd6-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="18bd6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18bd6-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="18bd6-111">Attributes</span></span>  
  
|<span data-ttu-id="18bd6-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="18bd6-112">Attribute</span></span>|<span data-ttu-id="18bd6-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18bd6-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="18bd6-114">PKT</span><span class="sxs-lookup"><span data-stu-id="18bd6-114">PKT</span></span>|<span data-ttu-id="18bd6-115">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="18bd6-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="18bd6-116">Specifica il token di chiave pubblica dell'assembly interessato, sotto forma di stringa.</span><span class="sxs-lookup"><span data-stu-id="18bd6-116">Specifies the public key token of the affected assembly, as a string.</span></span>|  
|<span data-ttu-id="18bd6-117">enabled</span><span class="sxs-lookup"><span data-stu-id="18bd6-117">enabled</span></span>|<span data-ttu-id="18bd6-118">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="18bd6-118">Optional attribute.</span></span><br /><br /> <span data-ttu-id="18bd6-119">Specifica se deve essere abilitato il supporto per la portabilità tra diverse implementazioni dell'assembly .NET Framework specificato.</span><span class="sxs-lookup"><span data-stu-id="18bd6-119">Specifies whether support for portability between implementations of the specified .NET Framework assembly should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="18bd6-120">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="18bd6-120">enabled Attribute</span></span>  
  
|<span data-ttu-id="18bd6-121">Valore</span><span class="sxs-lookup"><span data-stu-id="18bd6-121">Value</span></span>|<span data-ttu-id="18bd6-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18bd6-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="18bd6-123">true</span><span class="sxs-lookup"><span data-stu-id="18bd6-123">true</span></span>|<span data-ttu-id="18bd6-124">Abilitare il supporto per la portabilità tra diverse implementazioni dell'assembly .NET Framework specificato.</span><span class="sxs-lookup"><span data-stu-id="18bd6-124">Enable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="18bd6-125">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="18bd6-125">This is the default.</span></span>|  
|<span data-ttu-id="18bd6-126">False</span><span class="sxs-lookup"><span data-stu-id="18bd6-126">false</span></span>|<span data-ttu-id="18bd6-127">Disabilitare il supporto per la portabilità tra diverse implementazioni dell'assembly .NET Framework specificato.</span><span class="sxs-lookup"><span data-stu-id="18bd6-127">Disable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="18bd6-128">In questo modo l'applicazione affinché i riferimenti a più implementazioni dell'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="18bd6-128">This enables the application to have references to multiple implementations of the specified assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18bd6-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="18bd6-129">Child Elements</span></span>  
 <span data-ttu-id="18bd6-130">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="18bd6-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="18bd6-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="18bd6-131">Parent Elements</span></span>  
  
|<span data-ttu-id="18bd6-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="18bd6-132">Element</span></span>|<span data-ttu-id="18bd6-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18bd6-133">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="18bd6-134">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="18bd6-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="18bd6-135">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="18bd6-135">Contains information about assembly binding and garbage collection.</span></span>|  
|`assemblyBinding`|<span data-ttu-id="18bd6-136">Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.</span><span class="sxs-lookup"><span data-stu-id="18bd6-136">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18bd6-137">Note</span><span class="sxs-lookup"><span data-stu-id="18bd6-137">Remarks</span></span>  
 <span data-ttu-id="18bd6-138">A partire dal [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], il supporto viene fornito automaticamente per le applicazioni che è possono usare uno dei due implementazioni di .NET Framework, ad esempio l'implementazione di .NET Framework o .NET Framework per l'implementazione di Silverlight.</span><span class="sxs-lookup"><span data-stu-id="18bd6-138">Beginning with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], support is automatically provided for applications that can use either of two implementations of the .NET Framework, for example either the .NET Framework implementation or the .NET Framework for Silverlight implementation.</span></span> <span data-ttu-id="18bd6-139">Le due implementazioni di un particolare assembly di .NET Framework sono considerate equivalenti dal binder di assembly.</span><span class="sxs-lookup"><span data-stu-id="18bd6-139">The two implementations of a particular .NET Framework assembly are seen as equivalent by the assembly binder.</span></span> <span data-ttu-id="18bd6-140">In alcuni scenari, questa funzionalità di portabilità dell'applicazione può causare problemi.</span><span class="sxs-lookup"><span data-stu-id="18bd6-140">In a few scenarios, this application portability feature causes problems.</span></span> <span data-ttu-id="18bd6-141">In questi scenari il `<supportPortability>` elemento può essere usato per disabilitare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="18bd6-141">In those scenarios, the `<supportPortability>` element can be used to disable the feature.</span></span>  
  
 <span data-ttu-id="18bd6-142">Uno scenario di questo tipo è un assembly che deve fare riferimento sia l'implementazione di .NET Framework e .NET Framework per l'implementazione di Silverlight di un particolare assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="18bd6-142">One such scenario is an assembly that has to reference both the .NET Framework implementation and the .NET Framework for Silverlight implementation of a particular reference assembly.</span></span> <span data-ttu-id="18bd6-143">Ad esempio, una finestra di progettazione XAML scritta in Windows Presentation Foundation (WPF) potrebbe essere necessario fare riferimento a entrambi l'implementazione Desktop WPF, per interfaccia utente della finestra di progettazione e il subset di WPF è incluso nell'implementazione di Silverlight.</span><span class="sxs-lookup"><span data-stu-id="18bd6-143">For example, a XAML designer written in Windows Presentation Foundation (WPF) might need to reference both the WPF Desktop implementation, for the designer's user interface, and the subset of WPF that is included in the Silverlight implementation.</span></span> <span data-ttu-id="18bd6-144">Per impostazione predefinita, i riferimenti separati provocano un errore del compilatore, poiché l'associazione di assembly considera uguali i due assembly.</span><span class="sxs-lookup"><span data-stu-id="18bd6-144">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span> <span data-ttu-id="18bd6-145">Questo elemento consente di disattivare il comportamento predefinito e consente la compilazione abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="18bd6-145">This element disables the default behavior, and allows compilation to succeed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="18bd6-146">Affinché il compilatore può passare le informazioni per la logica di associazione degli assembly di common language runtime, è necessario usare il `/appconfig` opzione del compilatore per specificare il percorso del file app. config che contiene questo elemento.</span><span class="sxs-lookup"><span data-stu-id="18bd6-146">In order for the compiler to pass the information to the common language runtime's assembly-binding logic, you must use the `/appconfig` compiler option to specify the location of the app.config file that contains this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18bd6-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="18bd6-147">Example</span></span>  
 <span data-ttu-id="18bd6-148">L'esempio seguente Abilita i riferimenti sia l'implementazione di .NET Framework a .NET Framework per Silverlight per qualsiasi assembly di .NET Framework presente in entrambe le implementazioni a un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="18bd6-148">The following example enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="18bd6-149">Il `/appconfig` opzione del compilatore deve essere usata per specificare il percorso del file app. config.</span><span class="sxs-lookup"><span data-stu-id="18bd6-149">The `/appconfig` compiler option must be used to specify the location of this app.config file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="18bd6-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18bd6-150">See also</span></span>

- [<span data-ttu-id="18bd6-151">/appconfig (opzioni del compilatore c#)</span><span class="sxs-lookup"><span data-stu-id="18bd6-151">/appconfig (C# Compiler Options)</span></span>](../../../../../docs/csharp/language-reference/compiler-options/appconfig-compiler-option.md)
- <span data-ttu-id="18bd6-152">[Cenni preliminari sull'unificazione degli Assembly di .NET framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="18bd6-152">[.NET Framework Assembly Unification Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))</span></span>
