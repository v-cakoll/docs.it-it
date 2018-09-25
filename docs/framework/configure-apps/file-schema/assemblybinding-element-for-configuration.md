---
title: '&lt;assemblyBinding&gt; (elemento) per &lt;configurazione&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 5693b92ac35a357ff1f8643d0eb9ec2105acecb4
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47073463"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="e25b1-102">\<assemblyBinding > (elemento) per \<configuration ></span><span class="sxs-lookup"><span data-stu-id="e25b1-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="e25b1-103">Specifica i criteri di associazione degli assembly al livello di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e25b1-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="e25b1-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="e25b1-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="e25b1-105">&nbsp;&nbsp;**\<assemblyBinding >**</span><span class="sxs-lookup"><span data-stu-id="e25b1-105">&nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e25b1-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e25b1-106">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="e25b1-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="e25b1-107">Attribute</span></span>

|           | <span data-ttu-id="e25b1-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e25b1-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="e25b1-109">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="e25b1-109">**xmlns**</span></span> | <span data-ttu-id="e25b1-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e25b1-110">Required attribute.</span></span><br><br><span data-ttu-id="e25b1-111">Specifica lo spazio dei nomi XML necessario per il binding di assembly.</span><span class="sxs-lookup"><span data-stu-id="e25b1-111">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="e25b1-112">Usare la stringa "urn:schemas-microsoft-com:asm.v1" come valore.</span><span class="sxs-lookup"><span data-stu-id="e25b1-112">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="e25b1-113">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="e25b1-113">Parent element</span></span>

|     | <span data-ttu-id="e25b1-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e25b1-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="e25b1-115">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="e25b1-115">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="e25b1-116">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e25b1-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="e25b1-117">Elemento figlio</span><span class="sxs-lookup"><span data-stu-id="e25b1-117">Child element</span></span>

|     | <span data-ttu-id="e25b1-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e25b1-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="e25b1-119">**\<linkedConfiguration >**</span><span class="sxs-lookup"><span data-stu-id="e25b1-119">**\<linkedConfiguration>**</span></span>](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) | <span data-ttu-id="e25b1-120">Specifica un file di configurazione da includere.</span><span class="sxs-lookup"><span data-stu-id="e25b1-120">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="e25b1-121">Note</span><span class="sxs-lookup"><span data-stu-id="e25b1-121">Remarks</span></span>

<span data-ttu-id="e25b1-122">Il [  **\<linkedConfiguration >** ](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) elemento semplifica la gestione di assembly del componente, consentendo a file di configurazione in file di configurazione dell'applicazione per includere assembly percorsi noti, invece di duplicare le impostazioni di configurazione di assembly.</span><span class="sxs-lookup"><span data-stu-id="e25b1-122">The [**\<linkedConfiguration>**](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="e25b1-123">Il  **\<linkedConfiguration >** elemento non è supportato per le applicazioni con i manifesti side-by-side di Windows.</span><span class="sxs-lookup"><span data-stu-id="e25b1-123">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="e25b1-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="e25b1-124">Example</span></span>

<span data-ttu-id="e25b1-125">Nell'esempio seguente viene illustrato come includere un file di configurazione sul disco rigido locale:</span><span class="sxs-lookup"><span data-stu-id="e25b1-125">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="e25b1-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e25b1-126">See also</span></span>

[<span data-ttu-id="e25b1-127">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e25b1-127">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
