---
title: Estensione del sistema di metadati
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cab59f5ddebdcc1e50921d5540d411e32b562341
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="extending-the-metadata-system"></a><span data-ttu-id="06f41-102">Estensione del sistema di metadati</span><span class="sxs-lookup"><span data-stu-id="06f41-102">Extending the Metadata System</span></span>
<span data-ttu-id="06f41-103">Il sistema dei metadati di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] è un gruppo di classi e interfacce che rappresentano i metadati necessari per implementare applicazioni basate sul servizio.</span><span class="sxs-lookup"><span data-stu-id="06f41-103">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="06f41-104">Modificare o estendere le classi o implementare e configurare le interfacce per esportare e importare metadati personalizzati quali estensioni WSDL (Web Services Description Language) o asserzioni di WS-PolicyAttachments personalizzate.</span><span class="sxs-lookup"><span data-stu-id="06f41-104">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="06f41-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="06f41-105">In This Section</span></span>  
 [<span data-ttu-id="06f41-106">Esportazione di metadati personalizzati per un'estensione WCF</span><span class="sxs-lookup"><span data-stu-id="06f41-106">Exporting Custom Metadata for a WCF Extension</span></span>](../../../../docs/framework/wcf/extending/exporting-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="06f41-107">Viene descritto come implementare e utilizzare l'interfaccia <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> per incorporare asserzioni di criteri personalizzate nei documenti WSDL.</span><span class="sxs-lookup"><span data-stu-id="06f41-107">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interface to embed custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="06f41-108">Importazione di metadati personalizzati per un'estensione WCF</span><span class="sxs-lookup"><span data-stu-id="06f41-108">Importing Custom Metadata for a WCF Extension</span></span>](../../../../docs/framework/wcf/extending/importing-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="06f41-109">Viene descritto come implementare e utilizzare l'interfaccia <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> per leggere e rispondere ad asserzioni di criteri personalizzate in documenti WSDL.</span><span class="sxs-lookup"><span data-stu-id="06f41-109">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interface to read and respond to custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="06f41-110">La pubblicazione e recupero di metadati su un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="06f41-110">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 <span data-ttu-id="06f41-111">Viene descritto come scambiare metadati su associazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="06f41-111">Describes how to exchange metadata over custom bindings.</span></span>
