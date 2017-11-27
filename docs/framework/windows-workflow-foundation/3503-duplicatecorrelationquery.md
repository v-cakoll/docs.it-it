---
title: 3503 - DuplicateCorrelationQuery
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 60367b33e1e57cce8646b4fcde79c7d4fd20a4cc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="3503---duplicatecorrelationquery"></a>3503 - DuplicateCorrelationQuery
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|3503|  
|Parole chiave|WFServices|  
|Livello|Avviso|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Indica che è stato trovato un elemento CorrelationQuery duplicato. La query duplicata non verrà usata per il calcolo della correlazione.  
  
## <a name="message"></a>Messaggio  
 CorrelationQuery duplicata trovata con Where='%1'. La query duplicata non verrà usata per il calcolo della correlazione.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Dove|xs:string|La parte Where della query di correlazione.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
