---
title: Sezione di configurazione di Windows Form
ms.date: 04/07/2017
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18d8e1e24af73c9521b3a5bb45f1c86fc52ff1e9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755552"
---
# <a name="windows-forms-configuration-section"></a><span data-ttu-id="845c0-102">Sezione di configurazione di Windows Form</span><span class="sxs-lookup"><span data-stu-id="845c0-102">Windows Forms Configuration Section</span></span>
<span data-ttu-id="845c0-103">Le impostazioni di configurazione di Windows Form consentono a un'app Windows Form di archiviare e recuperare informazioni sulle impostazioni dell'applicazione personalizzate, ad esempio il supporto di più monitor, il supporto di valori DPI alti e altre impostazioni di configurazione predefinite.</span><span class="sxs-lookup"><span data-stu-id="845c0-103">Windows Forms configuration settings allow a Windows Forms app to store and retrieve information about customized application settings such as multi-monitor support, high DPI support, and other predefined configuration settings.</span></span>

<span data-ttu-id="845c0-104">Le impostazioni di configurazione dell'applicazione Windows Form sono archiviate in un elemento `System.Windows.Forms.ApplicationConfigurationSection` del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="845c0-104">Windows Forms application configuration settings are stored in an application configuration file's `System.Windows.Forms.ApplicationConfigurationSection` element.</span></span>

## <a name="syntax"></a><span data-ttu-id="845c0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="845c0-105">Syntax</span></span>

```xml
<configuration>
  <System.Windows.Forms.ApplicationConfigurationSection>
  ...
  </System.Windows.Forms.ApplicationConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="845c0-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="845c0-106">Attributes and elements</span></span>

<span data-ttu-id="845c0-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="845c0-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="845c0-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="845c0-108">Attributes</span></span>

<span data-ttu-id="845c0-109">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="845c0-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="845c0-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="845c0-110">Child elements</span></span>

<span data-ttu-id="845c0-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="845c0-111">Element</span></span>  |<span data-ttu-id="845c0-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="845c0-112">Description</span></span> |
---------|---------|
[`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) | <span data-ttu-id="845c0-113">Aggiunge una chiave per l'impostazione di configurazione con un valore specificato</span><span class="sxs-lookup"><span data-stu-id="845c0-113">Adds a configuration setting key with a specified value</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="845c0-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="845c0-114">Parent elements</span></span>

<span data-ttu-id="845c0-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="845c0-115">Element</span></span>  |<span data-ttu-id="845c0-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="845c0-116">Description</span></span> |
---------|---------|
[<span data-ttu-id="845c0-117">\<configuration></span><span class="sxs-lookup"><span data-stu-id="845c0-117">\<configuration></span></span>](../configuration-element.md) | <span data-ttu-id="845c0-118">Elemento radice in ogni file di configurazione usato in Common Language Runtime e nelle applicazioni Windows Form</span><span class="sxs-lookup"><span data-stu-id="845c0-118">The root element in every configuration file used by the common language runtime and Windows Forms applications</span></span> |

## <a name="remarks"></a><span data-ttu-id="845c0-119">Note</span><span class="sxs-lookup"><span data-stu-id="845c0-119">Remarks</span></span>

<span data-ttu-id="845c0-120">A partire da .NET Framework 4.7, l'elemento `<System.Windows.Forms.ApplicationConfigurationSection>` consente di configurare le applicazioni Windows Form in modo da sfruttare i vantaggi delle funzionalità aggiunte nelle versioni recenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="845c0-120">Starting with the .NET Framework 4.7, the `<System.Windows.Forms.ApplicationConfigurationSection>` element allows you to configure Windows Forms applications to take advantage of features added in recent releases of the .NET Framework.</span></span> 

<span data-ttu-id="845c0-121">L'elemento `<System.Windows.Forms.ApplicationConfigurationSection>` può includere uno o più elementi [ `<add>` ](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) figlio, ognuno dei quali definisce un'impostazione di configurazione specifica.</span><span class="sxs-lookup"><span data-stu-id="845c0-121">The `<System.Windows.Forms.ApplicationConfigurationSection>` element can include one or more child [`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) elements, each of which defines a specific configuration setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="845c0-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="845c0-122">See also</span></span>

<span data-ttu-id="845c0-123">[Schema dei file di configurazione](../index.md) </span><span class="sxs-lookup"><span data-stu-id="845c0-123">[Configuration File Schema](../index.md) </span></span>  
[<span data-ttu-id="845c0-124">Supporto di valori DPI alti in Windows Form</span><span class="sxs-lookup"><span data-stu-id="845c0-124">High DPI Support in Windows Forms</span></span>](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)
