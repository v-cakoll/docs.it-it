---
title: <supportPortability> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a76c378038a19d3edb9fe0c5e61012cc854c1b7
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72773936"
---
# <a name="supportportability-element"></a><span data-ttu-id="1a53f-102">Elemento \<supportPortability ></span><span class="sxs-lookup"><span data-stu-id="1a53f-102">\<supportPortability> Element</span></span>
<span data-ttu-id="1a53f-103">Specifica che un'applicazione può fare riferimento allo stesso assembly in due implementazioni diverse di .NET Framework, disabilitando il comportamento predefinito che tratta gli assembly come equivalenti per scopi di portabilità dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1a53f-103">Specifies that an application can reference the same assembly in two different implementations of the .NET Framework, by disabling the default behavior that treats the assemblies as equivalent for application portability purposes.</span></span>  
  
<span data-ttu-id="1a53f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1a53f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1a53f-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="1a53f-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="1a53f-106">&nbsp; &nbsp;[ \**&nbsp; &nbsp; \<assemblyBinding > \** ](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="1a53f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\</span></span>
<span data-ttu-id="1a53f-107">&nbsp; &nbsp; &nbsp; &nbsp; **&nbsp; &nbsp; \<supportPortability** ></span><span class="sxs-lookup"><span data-stu-id="1a53f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<supportPortability>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a53f-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1a53f-108">Syntax</span></span>  
  
```xml  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a53f-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1a53f-109">Attributes and Elements</span></span>  

<span data-ttu-id="1a53f-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1a53f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a53f-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="1a53f-111">Attributes</span></span>  
  
|<span data-ttu-id="1a53f-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="1a53f-112">Attribute</span></span>|<span data-ttu-id="1a53f-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1a53f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1a53f-114">PKT</span><span class="sxs-lookup"><span data-stu-id="1a53f-114">PKT</span></span>|<span data-ttu-id="1a53f-115">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1a53f-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="1a53f-116">Specifica il token di chiave pubblica dell'assembly interessato, sotto forma di stringa.</span><span class="sxs-lookup"><span data-stu-id="1a53f-116">Specifies the public key token of the affected assembly, as a string.</span></span>|  
|<span data-ttu-id="1a53f-117">enabled</span><span class="sxs-lookup"><span data-stu-id="1a53f-117">enabled</span></span>|<span data-ttu-id="1a53f-118">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1a53f-118">Optional attribute.</span></span><br /><br /> <span data-ttu-id="1a53f-119">Specifica se è necessario abilitare il supporto per la portabilità tra le implementazioni dell'assembly .NET Framework specificato.</span><span class="sxs-lookup"><span data-stu-id="1a53f-119">Specifies whether support for portability between implementations of the specified .NET Framework assembly should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="1a53f-120">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="1a53f-120">enabled Attribute</span></span>  
  
|<span data-ttu-id="1a53f-121">Value</span><span class="sxs-lookup"><span data-stu-id="1a53f-121">Value</span></span>|<span data-ttu-id="1a53f-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1a53f-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1a53f-123">true</span><span class="sxs-lookup"><span data-stu-id="1a53f-123">true</span></span>|<span data-ttu-id="1a53f-124">Abilita il supporto per la portabilità tra le implementazioni dell'assembly .NET Framework specificato.</span><span class="sxs-lookup"><span data-stu-id="1a53f-124">Enable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="1a53f-125">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1a53f-125">This is the default.</span></span>|  
|<span data-ttu-id="1a53f-126">False</span><span class="sxs-lookup"><span data-stu-id="1a53f-126">false</span></span>|<span data-ttu-id="1a53f-127">Disabilitare il supporto per la portabilità tra le implementazioni dell'assembly .NET Framework specificato.</span><span class="sxs-lookup"><span data-stu-id="1a53f-127">Disable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="1a53f-128">Ciò consente all'applicazione di avere riferimenti a più implementazioni dell'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="1a53f-128">This enables the application to have references to multiple implementations of the specified assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1a53f-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1a53f-129">Child Elements</span></span>  

<span data-ttu-id="1a53f-130">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="1a53f-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1a53f-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1a53f-131">Parent Elements</span></span>  
  
|<span data-ttu-id="1a53f-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="1a53f-132">Element</span></span>|<span data-ttu-id="1a53f-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1a53f-133">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1a53f-134">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1a53f-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="1a53f-135">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1a53f-135">Contains information about assembly binding and garbage collection.</span></span>|  
|`assemblyBinding`|<span data-ttu-id="1a53f-136">Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.</span><span class="sxs-lookup"><span data-stu-id="1a53f-136">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a53f-137">Note</span><span class="sxs-lookup"><span data-stu-id="1a53f-137">Remarks</span></span>  

<span data-ttu-id="1a53f-138">A partire da .NET Framework 4, il supporto viene fornito automaticamente per le applicazioni che possono usare una delle due implementazioni del .NET Framework, ad esempio l'implementazione di .NET Framework o la .NET Framework per l'implementazione di Silverlight.</span><span class="sxs-lookup"><span data-stu-id="1a53f-138">Beginning with the .NET Framework 4, support is automatically provided for applications that can use either of two implementations of the .NET Framework, for example either the .NET Framework implementation or the .NET Framework for Silverlight implementation.</span></span> <span data-ttu-id="1a53f-139">Le due implementazioni di un particolare assembly di .NET Framework sono considerate equivalenti dal binder di assembly.</span><span class="sxs-lookup"><span data-stu-id="1a53f-139">The two implementations of a particular .NET Framework assembly are seen as equivalent by the assembly binder.</span></span> <span data-ttu-id="1a53f-140">In alcuni scenari questa funzionalità di portabilità dell'applicazione causa problemi.</span><span class="sxs-lookup"><span data-stu-id="1a53f-140">In a few scenarios, this application portability feature causes problems.</span></span> <span data-ttu-id="1a53f-141">In questi scenari, è possibile usare l'elemento `<supportPortability>` per disabilitare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="1a53f-141">In those scenarios, the `<supportPortability>` element can be used to disable the feature.</span></span>  
  
<span data-ttu-id="1a53f-142">Uno di questi scenari è costituito da un assembly che deve fare riferimento sia all'implementazione di .NET Framework sia al .NET Framework per l'implementazione Silverlight di un particolare assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="1a53f-142">One such scenario is an assembly that has to reference both the .NET Framework implementation and the .NET Framework for Silverlight implementation of a particular reference assembly.</span></span> <span data-ttu-id="1a53f-143">Ad esempio, una finestra di progettazione XAML scritta in Windows Presentation Foundation (WPF) potrebbe dover fare riferimento sia all'implementazione desktop WPF, per l'interfaccia utente della finestra di progettazione, sia al subset di WPF incluso nell'implementazione di Silverlight.</span><span class="sxs-lookup"><span data-stu-id="1a53f-143">For example, a XAML designer written in Windows Presentation Foundation (WPF) might need to reference both the WPF Desktop implementation, for the designer's user interface, and the subset of WPF that is included in the Silverlight implementation.</span></span> <span data-ttu-id="1a53f-144">Per impostazione predefinita, i riferimenti separati provocano un errore del compilatore, poiché l'associazione di assembly considera uguali i due assembly.</span><span class="sxs-lookup"><span data-stu-id="1a53f-144">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span> <span data-ttu-id="1a53f-145">Questo elemento Disabilita il comportamento predefinito e consente la compilazione in modo che abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="1a53f-145">This element disables the default behavior, and allows compilation to succeed.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1a53f-146">Per consentire al compilatore di passare le informazioni alla logica di associazione degli assembly del Common Language Runtime, è necessario usare l'opzione del compilatore `/appconfig` per specificare il percorso del file app. config che contiene questo elemento.</span><span class="sxs-lookup"><span data-stu-id="1a53f-146">In order for the compiler to pass the information to the common language runtime's assembly-binding logic, you must use the `/appconfig` compiler option to specify the location of the app.config file that contains this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a53f-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="1a53f-147">Example</span></span>  

<span data-ttu-id="1a53f-148">Nell'esempio seguente viene abilitata un'applicazione per avere riferimenti sia all'implementazione di .NET Framework sia al .NET Framework per l'implementazione Silverlight di qualsiasi assembly .NET Framework esistente in entrambe le implementazioni.</span><span class="sxs-lookup"><span data-stu-id="1a53f-148">The following example enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="1a53f-149">Per specificare il percorso del file app. config, è necessario usare l'opzione del compilatore `/appconfig`.</span><span class="sxs-lookup"><span data-stu-id="1a53f-149">The `/appconfig` compiler option must be used to specify the location of this app.config file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1a53f-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a53f-150">See also</span></span>

- [<span data-ttu-id="1a53f-151">-appconfig (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="1a53f-151">-appconfig (C# Compiler Options)</span></span>](../../../../csharp/language-reference/compiler-options/appconfig-compiler-option.md)
- <span data-ttu-id="1a53f-152">[Panoramica dell'unificazione degli assembly .NET Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1a53f-152">[.NET Framework Assembly Unification Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))</span></span>
