---
title: Classe Operation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 739f8309e7a01eeecf921b50fcde24417fbbc515
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="operation-class"></a>Classe Operation
Operazione  
  
## <a name="syntax"></a>Sintassi  
  
```  
class Operation  
{  
  string Action;  
  boolean AsyncPattern;  
  Behavior Behaviors[];  
  boolean IsCallback;  
  boolean IsInitiating;  
  boolean IsOneWay;  
  boolean IsTerminating;  
  string MethodSignature;  
  string Name;  
  string ParameterTypes[];  
  string ReplyAction;  
  string ReturnType;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe Operation non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe Operation ha le proprietà seguenti:  
  
### <a name="action"></a>Operazione  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Azione WS-Addressing del messaggio di richiesta.  
  
### <a name="asyncpattern"></a>AsyncPattern  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Indica che un'operazione è implementata in modo asincrono utilizzando un `Begin`[parentesi angolari aperte/chiuse] e `End`coppia di metodi [parentesi angolari aperte/chiuse] in un contratto di servizio.  
  
### <a name="behaviors"></a>Comportamenti  
 Tipo di dati: matrice di Behavior  
  
 Tipo di accesso: sola lettura  
  
 Comportamenti associati all'operazione.  
  
### <a name="iscallback"></a>IsCallback  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Restituisce True quando l'operazione è un'operazione di callback.  
  
### <a name="isinitiating"></a>IsInitiating  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Indica se il metodo implementa un'operazione in grado di avviare una sessione nel server.  
  
### <a name="isoneway"></a>IsOneWay  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Indica se un'operazione restituisce un messaggio di risposta.  
  
### <a name="isterminating"></a>IsTerminating  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Indica se un'operazione restituisce un messaggio di risposta.  
  
### <a name="methodsignature"></a>MethodSignature  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Firma del metodo dell'operazione.  
  
### <a name="name"></a>Nome  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Nome dell'operazione.  
  
### <a name="parametertypes"></a>ParameterTypes  
 Tipo di dati: matrice di stringhe  
  
 Tipo di accesso: sola lettura  
  
 Tipi dei parametri dell'operazione.  
  
### <a name="replyaction"></a>ReplyAction  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Valore dell'azione SOAP del messaggio di risposta dell'operazione.  
  
### <a name="returntype"></a>ReturnType  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Tipo restituito dall'operazione.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Description.OperationDescription>
