---
title: Estensione del sistema di metadati
ms.date: 03/30/2017
helpviewer_keywords:
- extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
ms.openlocfilehash: d3ce7e1a228e6303be1009c7b72f4e889b40c536
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795716"
---
# <a name="extending-the-metadata-system"></a>Estensione del sistema di metadati
Il sistema di metadati Windows Communication Foundation (WCF) è un gruppo di classi e interfacce che rappresentano i metadati necessari per implementare applicazioni basate su servizi. Modificare o estendere le classi o implementare e configurare le interfacce per esportare e importare metadati personalizzati quali estensioni WSDL (Web Services Description Language) o asserzioni di WS-PolicyAttachments personalizzate.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Esportazione di metadati personalizzati per un'estensione WCF](exporting-custom-metadata-for-a-wcf-extension.md)  
 Viene descritto come implementare e utilizzare l'interfaccia <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> per incorporare asserzioni di criteri personalizzate nei documenti WSDL.  
  
 [Importazione di metadati personalizzati per un'estensione WCF](importing-custom-metadata-for-a-wcf-extension.md)  
 Viene descritto come implementare e utilizzare l'interfaccia <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> per leggere e rispondere ad asserzioni di criteri personalizzate in documenti WSDL.  
  
 [Pubblicazione e recupero di metadati su un'associazione personalizzata](publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 Viene descritto come scambiare metadati su associazioni personalizzate.
