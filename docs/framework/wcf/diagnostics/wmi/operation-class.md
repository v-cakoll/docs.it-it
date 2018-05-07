---
title: Classe Operation
ms.date: 03/30/2017
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
ms.openlocfilehash: d9256915afe9fdb8e4c91d186131fe41a7094c56
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
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
  
### <a name="behaviors"></a>comportamenti  
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
  
### <a name="name"></a>nome  
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
