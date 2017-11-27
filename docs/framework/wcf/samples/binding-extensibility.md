---
title: "Estensibilità delle associazioni"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cabdd583-ddf5-493e-9dba-c6c31cde8f65
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 61c8ae647012c5f1fffe5cf65c63b64cde62af1b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="binding-extensibility"></a>Estensibilità delle associazioni
Contenuto della sezione sono inclusi esempi che illustrano l'associazione personalizzata in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 <xref:System.ServiceModel.NetHttpBinding>  
 Viene illustrato come implementare un'associazione che posiziona <xref:System.ServiceModel.Channels.HttpTransportBindingElement> o <xref:System.ServiceModel.Channels.HttpsTransportBindingElement> in cima allo stack di <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>.  
  
 <!--zz <xref:System.ServiceModel.WSStreamedHttpBinding> --> `System.ServiceModel.WSStreamedHttpBinding` 
 Nell'esempio viene illustrato come creare un'associazione progettata per supportare scenari basati sul flusso quando viene usato il trasporto HTTP.
