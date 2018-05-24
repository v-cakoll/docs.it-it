---
title: Esposizione di componenti .NET Framework a COM
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET Framework components to COM
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: e42a65f7-1e61-411f-b09a-aca1bbce24c6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f11928388dba9b0e9b442578bfb7b6f751c2e172
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="exposing-net-framework-components-to-com"></a>Esposizione di componenti .NET Framework a COM
La scrittura di un tipo .NET e l'utilizzo di tale tipo dal codice non gestito sono attività distinte per gli sviluppatori. Questa sezione offre diversi suggerimenti per la scrittura di un codice gestito che interagisce con i client COM:  
  
-   [Qualificazione di tipi .NET per l'interoperabilità](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md).  
  
     Tutti i tipi gestiti, i metodi, le proprietà, i campi e gli eventi che si vuole esporre a COM devono essere pubblici. I tipi devono avere un costruttore predefinito pubblico, che è l'unico costruttore a poter essere richiamato tramite COM.  
  
-   [Applicazione di attributi di interoperabilità](../../../docs/framework/interop/applying-interop-attributes.md).  
  
     Gli attributi personalizzati nel codice gestito possono migliorare l'interoperabilità di un componente.  
  
-   [Preparazione di un assembly per COM](../../../docs/framework/interop/packaging-an-assembly-for-com.md).  
  
     Gli sviluppatori COM potrebbero richiedere di riepilogare i passaggi previsti per fare riferimento agli assembly e distribuirli.  
  
 Questa sezione indica anche le attività relative all'utilizzo di un tipo gestito da un client COM.  
  
#### <a name="to-consume-a-managed-type-from-com"></a>Per utilizzare un tipo gestito da COM  
  
1.  [Registrare gli assembly con COM](../../../docs/framework/interop/registering-assemblies-with-com.md).  
  
     I tipi in un assembly (e le librerie dei tipi) devono essere registrati in fase di progettazione. Se un programma di installazione non registra l'assembly, comunicare agli sviluppatori COM di usare Regasm.exe.  
  
2.  [Fare riferimento a tipi .NET da COM](../../../docs/framework/interop/how-to-reference-net-types-from-com.md).  
  
     Gli sviluppatori COM possono fare riferimento ai tipi in un assembly usando gli strumenti e le tecniche abituali.  
  
3.  [Chiamare un oggetto .NET](https://msdn.microsoft.com/library/40c9626c-aea6-4bad-b8f0-c1de462efd33(v=vs.100)).  
  
     Gli sviluppatori COM possono chiamare i metodi sull'oggetto .NET nello stesso modo in cui chiamano i metodi sui tipi non gestiti. Ad esempio, l'API **CoCreateInstance** COM attiva gli oggetti .NET.  
  
4.  [Distribuire un'applicazione per l'accesso COM](https://msdn.microsoft.com/library/fb63564c-c1b9-4655-a094-a235625882ce(v=vs.100)).  
  
     Un assembly con nome sicuro può essere installato nella Global Assembly Cache e richiede una firma dall'entità di pubblicazione. Gli assembly privi di nome sicuro devono essere installati nella directory dell'applicazione del client.  
  
## <a name="see-also"></a>Vedere anche  
 [Interoperabilità con codice non gestito](../../../docs/framework/interop/index.md)  
 [Esempio di interoperabilità: client COM e server .NET](../../../docs/framework/interop/com-interop-sample-com-client-and-net-server.md)
