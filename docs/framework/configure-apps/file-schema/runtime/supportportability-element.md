---
title: <supportPortability> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
ms.openlocfilehash: 63c309a8a93c1d31ed8f73a495cf5154c3590d56
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73115647"
---
# <a name="supportportability-element"></a><span data-ttu-id="4fe36-102">\<supportPortability> Elemento</span><span class="sxs-lookup"><span data-stu-id="4fe36-102">\<supportPortability> Element</span></span>
<span data-ttu-id="4fe36-103">Specifica che un'applicazione può fare riferimento allo stesso assembly in due implementazioni diverse di .NET Framework, disabilitando il comportamento predefinito che tratta gli assembly come equivalenti per scopi di portabilità dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4fe36-103">Specifies that an application can reference the same assembly in two different implementations of the .NET Framework, by disabling the default behavior that treats the assemblies as equivalent for application portability purposes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<supportPortability>**  
  
## <a name="syntax"></a><span data-ttu-id="4fe36-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4fe36-104">Syntax</span></span>  
  
```xml  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4fe36-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4fe36-105">Attributes and Elements</span></span>  

<span data-ttu-id="4fe36-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4fe36-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4fe36-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="4fe36-107">Attributes</span></span>  
  
|<span data-ttu-id="4fe36-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="4fe36-108">Attribute</span></span>|<span data-ttu-id="4fe36-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4fe36-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4fe36-110">PKT</span><span class="sxs-lookup"><span data-stu-id="4fe36-110">PKT</span></span>|<span data-ttu-id="4fe36-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4fe36-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="4fe36-112">Specifica il token di chiave pubblica dell'assembly interessato, sotto forma di stringa.</span><span class="sxs-lookup"><span data-stu-id="4fe36-112">Specifies the public key token of the affected assembly, as a string.</span></span>|  
|<span data-ttu-id="4fe36-113">Enabled</span><span class="sxs-lookup"><span data-stu-id="4fe36-113">enabled</span></span>|<span data-ttu-id="4fe36-114">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4fe36-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4fe36-115">Specifica se è necessario abilitare il supporto per la portabilità tra le implementazioni dell'assembly .NET Framework specificato.</span><span class="sxs-lookup"><span data-stu-id="4fe36-115">Specifies whether support for portability between implementations of the specified .NET Framework assembly should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="4fe36-116">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="4fe36-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="4fe36-117">Valore</span><span class="sxs-lookup"><span data-stu-id="4fe36-117">Value</span></span>|<span data-ttu-id="4fe36-118">Description</span><span class="sxs-lookup"><span data-stu-id="4fe36-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4fe36-119">true</span><span class="sxs-lookup"><span data-stu-id="4fe36-119">true</span></span>|<span data-ttu-id="4fe36-120">Abilita il supporto per la portabilità tra le implementazioni dell'assembly .NET Framework specificato.</span><span class="sxs-lookup"><span data-stu-id="4fe36-120">Enable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="4fe36-121">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="4fe36-121">This is the default.</span></span>|  
|<span data-ttu-id="4fe36-122">false</span><span class="sxs-lookup"><span data-stu-id="4fe36-122">false</span></span>|<span data-ttu-id="4fe36-123">Disabilitare il supporto per la portabilità tra le implementazioni dell'assembly .NET Framework specificato.</span><span class="sxs-lookup"><span data-stu-id="4fe36-123">Disable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="4fe36-124">Ciò consente all'applicazione di avere riferimenti a più implementazioni dell'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="4fe36-124">This enables the application to have references to multiple implementations of the specified assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4fe36-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4fe36-125">Child Elements</span></span>  

<span data-ttu-id="4fe36-126">No.</span><span class="sxs-lookup"><span data-stu-id="4fe36-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4fe36-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4fe36-127">Parent Elements</span></span>  
  
|<span data-ttu-id="4fe36-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="4fe36-128">Element</span></span>|<span data-ttu-id="4fe36-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4fe36-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4fe36-130">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4fe36-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4fe36-131">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4fe36-131">Contains information about assembly binding and garbage collection.</span></span>|  
|`assemblyBinding`|<span data-ttu-id="4fe36-132">Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.</span><span class="sxs-lookup"><span data-stu-id="4fe36-132">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4fe36-133">Commenti</span><span class="sxs-lookup"><span data-stu-id="4fe36-133">Remarks</span></span>  

<span data-ttu-id="4fe36-134">A partire da .NET Framework 4, il supporto viene fornito automaticamente per le applicazioni che possono usare una delle due implementazioni del .NET Framework, ad esempio l'implementazione di .NET Framework o la .NET Framework per l'implementazione di Silverlight.</span><span class="sxs-lookup"><span data-stu-id="4fe36-134">Beginning with the .NET Framework 4, support is automatically provided for applications that can use either of two implementations of the .NET Framework, for example either the .NET Framework implementation or the .NET Framework for Silverlight implementation.</span></span> <span data-ttu-id="4fe36-135">Le due implementazioni di un particolare assembly di .NET Framework sono considerate equivalenti dal binder di assembly.</span><span class="sxs-lookup"><span data-stu-id="4fe36-135">The two implementations of a particular .NET Framework assembly are seen as equivalent by the assembly binder.</span></span> <span data-ttu-id="4fe36-136">In alcuni scenari questa funzionalità di portabilità dell'applicazione causa problemi.</span><span class="sxs-lookup"><span data-stu-id="4fe36-136">In a few scenarios, this application portability feature causes problems.</span></span> <span data-ttu-id="4fe36-137">In questi scenari, l' `<supportPortability>` elemento può essere usato per disabilitare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="4fe36-137">In those scenarios, the `<supportPortability>` element can be used to disable the feature.</span></span>  
  
<span data-ttu-id="4fe36-138">Uno di questi scenari è costituito da un assembly che deve fare riferimento sia all'implementazione di .NET Framework sia al .NET Framework per l'implementazione Silverlight di un particolare assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="4fe36-138">One such scenario is an assembly that has to reference both the .NET Framework implementation and the .NET Framework for Silverlight implementation of a particular reference assembly.</span></span> <span data-ttu-id="4fe36-139">Ad esempio, una finestra di progettazione XAML scritta in Windows Presentation Foundation (WPF) potrebbe dover fare riferimento sia all'implementazione desktop WPF, per l'interfaccia utente della finestra di progettazione, sia al subset di WPF incluso nell'implementazione di Silverlight.</span><span class="sxs-lookup"><span data-stu-id="4fe36-139">For example, a XAML designer written in Windows Presentation Foundation (WPF) might need to reference both the WPF Desktop implementation, for the designer's user interface, and the subset of WPF that is included in the Silverlight implementation.</span></span> <span data-ttu-id="4fe36-140">Per impostazione predefinita, i riferimenti separati provocano un errore del compilatore, poiché l'associazione di assembly considera uguali i due assembly.</span><span class="sxs-lookup"><span data-stu-id="4fe36-140">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span> <span data-ttu-id="4fe36-141">Questo elemento Disabilita il comportamento predefinito e consente la compilazione in modo che abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="4fe36-141">This element disables the default behavior, and allows compilation to succeed.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4fe36-142">Affinché il compilatore passi le informazioni alla logica di associazione degli assembly del Common Language Runtime, è necessario usare l' `/appconfig` opzione del compilatore per specificare il percorso del file app. config che contiene questo elemento.</span><span class="sxs-lookup"><span data-stu-id="4fe36-142">In order for the compiler to pass the information to the common language runtime's assembly-binding logic, you must use the `/appconfig` compiler option to specify the location of the app.config file that contains this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4fe36-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="4fe36-143">Example</span></span>  

<span data-ttu-id="4fe36-144">Nell'esempio seguente viene abilitata un'applicazione per avere riferimenti sia all'implementazione di .NET Framework sia al .NET Framework per l'implementazione Silverlight di qualsiasi assembly .NET Framework esistente in entrambe le implementazioni.</span><span class="sxs-lookup"><span data-stu-id="4fe36-144">The following example enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="4fe36-145">`/appconfig`Per specificare il percorso del file app. config, è necessario usare l'opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="4fe36-145">The `/appconfig` compiler option must be used to specify the location of this app.config file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4fe36-146">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="4fe36-146">See also</span></span>

- [<span data-ttu-id="4fe36-147">-appconfig (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="4fe36-147">-appconfig (C# Compiler Options)</span></span>](../../../../csharp/language-reference/compiler-options/appconfig-compiler-option.md)
- <span data-ttu-id="4fe36-148">[Cenni preliminari sull'unificazione degli assembly .NET Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4fe36-148">[.NET Framework Assembly Unification Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))</span></span>
