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
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47193356"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="fc804-102">\<assemblyBinding > (elemento) per \<configuration ></span><span class="sxs-lookup"><span data-stu-id="fc804-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="fc804-103">Specifica i criteri di associazione degli assembly al livello di configurazione.</span><span class="sxs-lookup"><span data-stu-id="fc804-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="fc804-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="fc804-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="fc804-105">&nbsp;&nbsp;**\<assemblyBinding >**</span><span class="sxs-lookup"><span data-stu-id="fc804-105">&nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="fc804-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc804-106">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="fc804-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="fc804-107">Attribute</span></span>

|           | <span data-ttu-id="fc804-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc804-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="fc804-109">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="fc804-109">**xmlns**</span></span> | <span data-ttu-id="fc804-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fc804-110">Required attribute.</span></span><br><br><span data-ttu-id="fc804-111">Specifica lo spazio dei nomi XML necessario per il binding di assembly.</span><span class="sxs-lookup"><span data-stu-id="fc804-111">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="fc804-112">Usare la stringa "urn:schemas-microsoft-com:asm.v1" come valore.</span><span class="sxs-lookup"><span data-stu-id="fc804-112">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="fc804-113">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="fc804-113">Parent element</span></span>

|     | <span data-ttu-id="fc804-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc804-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="fc804-115">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="fc804-115">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="fc804-116">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fc804-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="fc804-117">Elemento figlio</span><span class="sxs-lookup"><span data-stu-id="fc804-117">Child element</span></span>

|     | <span data-ttu-id="fc804-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc804-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="fc804-119">**\<linkedConfiguration >**</span><span class="sxs-lookup"><span data-stu-id="fc804-119">**\<linkedConfiguration>**</span></span>](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) | <span data-ttu-id="fc804-120">Specifica un file di configurazione da includere.</span><span class="sxs-lookup"><span data-stu-id="fc804-120">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="fc804-121">Note</span><span class="sxs-lookup"><span data-stu-id="fc804-121">Remarks</span></span>

<span data-ttu-id="fc804-122">Il [  **\<linkedConfiguration >** ](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) elemento semplifica la gestione di assembly del componente, consentendo a file di configurazione in file di configurazione dell'applicazione per includere assembly percorsi noti, invece di duplicare le impostazioni di configurazione di assembly.</span><span class="sxs-lookup"><span data-stu-id="fc804-122">The [**\<linkedConfiguration>**](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="fc804-123">Il  **\<linkedConfiguration >** elemento non è supportato per le applicazioni con i manifesti side-by-side di Windows.</span><span class="sxs-lookup"><span data-stu-id="fc804-123">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="fc804-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="fc804-124">Example</span></span>

<span data-ttu-id="fc804-125">Nell'esempio seguente viene illustrato come includere un file di configurazione sul disco rigido locale:</span><span class="sxs-lookup"><span data-stu-id="fc804-125">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="fc804-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc804-126">See also</span></span>

[<span data-ttu-id="fc804-127">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fc804-127">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
