---
title: "Procedura: Impostare criteri di cache predefiniti basati sull'ora per un'applicazione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time-based cache policies
- cache [.NET Framework], time-based policies
- default time-based cache policy
ms.assetid: 6bfce066-a2e7-4add-a05e-85c12ec9f07f
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 021a13b9124cf54712643e33cbf0ca77ec828b27
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-the-default-time-based-cache-policy-for-an-application"></a>Procedura: Impostare criteri di cache predefiniti basati sull'ora per un'applicazione
I criteri di cache basati sul tempo predefiniti consentono di definire il comportamento della cache per un'applicazione in base alle intestazioni inviate con la risorsa memorizzata nella cache e al comportamento della cache definito nelle sezioni 13 e 14 del documento RFC 2616, disponibile all'indirizzo [http://www.ietf.org](http://www.ietf.org/). Questo è il comportamento della cache appropriato per la maggior parte delle applicazioni.  
  
### <a name="to-set-the-default-automatic-policy-for-an-application"></a>Per impostare i criteri automatici predefiniti per un'applicazione  
  
1.  Creare un oggetto criteri basati sul tempo predefinito.  
  
2.  Impostare l'oggetto criteri come predefinito per il dominio dell'applicazione.  
  
## <a name="example"></a>Esempio  
 I due esempi in questa sezione producono criteri identici.  
  
 L'esempio seguente crea un criterio basato sul tempo predefinito e lo imposta come predefinito per il dominio dell'applicazione.  
  
```csharp  
public static void SetDefaultTimeBasedPolicy ()  
{  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy ();  
    HttpWebRequest.DefaultCachePolicy = policy ;  
}  
```  
  
```vb  
Public Shared Sub SetDefaultTimeBasedPolicy ()  
    Dim policy = New HttpRequestCachePolicy ()  
    HttpWebRequest.DefaultCachePolicy = policy  
End Sub  
```  
  
 È anche possibile creare criteri di cache basati sul tempo predefiniti usando la classe <xref:System.Net.Cache.RequestCachePolicy> come illustrato nell'esempio seguente:  
  
```csharp  
public static void SetDefaultTimeBasedPolicy2()  
{  
    RequestCachePolicy policy = new RequestCachePolicy ();  
    HttpWebRequest.DefaultCachePolicy = policy ;  
}  
```  
  
```vb  
Public Shared Sub SetDefaultTimeBasedPolicy2()  
    Dim policy As New RequestCachePolicy()  
    HttpWebRequest.DefaultCachePolicy = policy  
End Sub  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Gestione della cache per le applicazioni di rete](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [Criteri di cache](../../../docs/framework/network-programming/cache-policy.md)  
 [Criteri di cache basati sulla posizione](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [Criteri di cache basati sull'ora](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 [Elemento \<requestCaching> (impostazioni di rete)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
