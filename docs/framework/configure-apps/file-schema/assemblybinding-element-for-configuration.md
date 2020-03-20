---
title: Elemento <assemblyBinding> per <configuration>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: 21cf5e749b0dae310c3326f8abf82c6678fc97e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155479"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="4edff-102">\<elemento> assemblyBinding per \<la> configurazione</span><span class="sxs-lookup"><span data-stu-id="4edff-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="4edff-103">Specifica i criteri di associazione degli assembly al livello di configurazione.</span><span class="sxs-lookup"><span data-stu-id="4edff-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="4edff-104">[\*\* \<>\*\*](configuration-element.md) &nbsp; &nbsp; **assemblyBinding>\<**</span><span class="sxs-lookup"><span data-stu-id="4edff-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="4edff-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4edff-105">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="4edff-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="4edff-106">Attribute</span></span>

|           | <span data-ttu-id="4edff-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4edff-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="4edff-108">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="4edff-108">**xmlns**</span></span> | <span data-ttu-id="4edff-109">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4edff-109">Required attribute.</span></span><br><br><span data-ttu-id="4edff-110">Specifica lo spazio dei nomi XML necessario per il binding di assembly.</span><span class="sxs-lookup"><span data-stu-id="4edff-110">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="4edff-111">Usare la stringa "urn:schemas-microsoft-com:asm.v1" come valore.</span><span class="sxs-lookup"><span data-stu-id="4edff-111">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="4edff-112">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="4edff-112">Parent element</span></span>

|     | <span data-ttu-id="4edff-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4edff-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="4edff-114">**\<>di configurazione**</span><span class="sxs-lookup"><span data-stu-id="4edff-114">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="4edff-115">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4edff-115">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="4edff-116">Elemento figlio</span><span class="sxs-lookup"><span data-stu-id="4edff-116">Child element</span></span>

|     | <span data-ttu-id="4edff-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4edff-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="4edff-118">**\<>linkedConfiguration**</span><span class="sxs-lookup"><span data-stu-id="4edff-118">**\<linkedConfiguration>**</span></span>](linkedconfiguration-element.md) | <span data-ttu-id="4edff-119">Specifica un file di configurazione da includere.</span><span class="sxs-lookup"><span data-stu-id="4edff-119">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="4edff-120">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4edff-120">Remarks</span></span>

<span data-ttu-id="4edff-121">Il [\*\* \<>elemento linkedConfiguration\*\*](linkedconfiguration-element.md) semplifica la gestione degli assembly dei componenti consentendo ai file di configurazione dell'applicazione di includere i file di configurazione dell'assembly in percorsi noti, anziché duplicare le impostazioni di configurazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="4edff-121">The [**\<linkedConfiguration>**](linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="4edff-122">L'elemento \*\* \<>linkedConfiguration\*\* non è supportato per le applicazioni con manifesti affiancati di Windows.The linkedConfiguration>element is not supported for applications with Windows side-by-side manifests.</span><span class="sxs-lookup"><span data-stu-id="4edff-122">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="4edff-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="4edff-123">Example</span></span>

<span data-ttu-id="4edff-124">L'esempio seguente mostra come includere un file di configurazione sul disco rigido locale:</span><span class="sxs-lookup"><span data-stu-id="4edff-124">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="4edff-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4edff-125">See also</span></span>

- [<span data-ttu-id="4edff-126">Schema del file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4edff-126">Configuration file schema for the .NET Framework</span></span>](index.md)
