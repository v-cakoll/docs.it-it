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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155479"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="7aca4-102">Elemento \<assemblyBinding> per \<configuration></span><span class="sxs-lookup"><span data-stu-id="7aca4-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="7aca4-103">Specifica i criteri di associazione degli assembly al livello di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7aca4-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="7aca4-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<assemblyBinding>**</span><span class="sxs-lookup"><span data-stu-id="7aca4-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="7aca4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7aca4-105">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="7aca4-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="7aca4-106">Attribute</span></span>

|           | <span data-ttu-id="7aca4-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7aca4-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="7aca4-108">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="7aca4-108">**xmlns**</span></span> | <span data-ttu-id="7aca4-109">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7aca4-109">Required attribute.</span></span><br><br><span data-ttu-id="7aca4-110">Specifica lo spazio dei nomi XML necessario per il binding di assembly.</span><span class="sxs-lookup"><span data-stu-id="7aca4-110">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="7aca4-111">Usare la stringa "urn:schemas-microsoft-com:asm.v1" come valore.</span><span class="sxs-lookup"><span data-stu-id="7aca4-111">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="7aca4-112">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="7aca4-112">Parent element</span></span>

|     | <span data-ttu-id="7aca4-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7aca4-113">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="7aca4-114">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7aca4-114">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="7aca4-115">Elemento figlio</span><span class="sxs-lookup"><span data-stu-id="7aca4-115">Child element</span></span>

|     | <span data-ttu-id="7aca4-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7aca4-116">Description</span></span> |
| --- | ----------- |
| [**\<linkedConfiguration>**](linkedconfiguration-element.md) | <span data-ttu-id="7aca4-117">Specifica un file di configurazione da includere.</span><span class="sxs-lookup"><span data-stu-id="7aca4-117">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="7aca4-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="7aca4-118">Remarks</span></span>

<span data-ttu-id="7aca4-119">L' [**\<linkedConfiguration>**](linkedconfiguration-element.md) elemento semplifica la gestione degli assembly dei componenti consentendo ai file di configurazione dell'applicazione di includere i file di configurazione degli assembly in posizioni note, anziché duplicare le impostazioni di configurazione degli assembly.</span><span class="sxs-lookup"><span data-stu-id="7aca4-119">The [**\<linkedConfiguration>**](linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="7aca4-120">L' **\<linkedConfiguration>** elemento non è supportato per le applicazioni con manifesti affiancati di Windows.</span><span class="sxs-lookup"><span data-stu-id="7aca4-120">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="7aca4-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="7aca4-121">Example</span></span>

<span data-ttu-id="7aca4-122">Nell'esempio seguente viene illustrato come includere un file di configurazione nel disco rigido locale:</span><span class="sxs-lookup"><span data-stu-id="7aca4-122">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="7aca4-123">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="7aca4-123">See also</span></span>

- [<span data-ttu-id="7aca4-124">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7aca4-124">Configuration file schema for the .NET Framework</span></span>](index.md)
