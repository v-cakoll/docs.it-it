---
title: 'Mitigazione: Protocolli TLS'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 33f97d13-3022-43da-8b18-cdb5c88df9c2
ms.openlocfilehash: 45225d73ac60564d3e22c73270faab6b4e04d697
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73457832"
---
# <a name="mitigation-tls-protocols"></a>Mitigazione: Protocolli TLS
A partire da .NET Framework 4.6, le classi <xref:System.Net.ServicePointManager?displayProperty=nameWithType> e <xref:System.Net.Security.SslStream?displayProperty=nameWithType> possono usare uno dei tre protocolli seguenti: Tls1.0, Tls1.1 o Tls 1.2. Il protocollo SSL 3.0 e la crittografia RC4 non sono supportati.  
  
## <a name="impact"></a>Impatto  
 Questa modifica interessa:  
  
- Qualsiasi app che usa SSL per comunicare con un server HTTPS o un server socket tramite uno qualsiasi dei tipi seguenti: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient> e <xref:System.Net.Security.SslStream>.  
  
- Qualsiasi app sul lato server che non può essere aggiornata per supportare Tls1.0, Tls1.1 o Tls 1.2.  
  
## <a name="mitigation"></a>Strategia di riduzione del rischio  
 L'attenuazione consigliata consiste nell'aggiornare l'app sul lato server a Tls1.0, Tls1.1 o Tls 1.2. Se ciò non è fattibile o se le app client non funzionano, è possibile usare la classe <xref:System.AppContext> per rifiutare esplicitamente questa funzionalità in uno dei due modi seguenti:  
  
- A livello di codice, usando un frammento di codice simile al seguente:  
  
     [!code-csharp[AppCompat.SSLProtocols#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.sslprotocols/cs/program.cs#1)]
     [!code-vb[AppCompat.SSLProtocols#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.sslprotocols/vb/module1.vb#1)]  
  
     Poiché l'oggetto <xref:System.Net.ServicePointManager> viene inizializzato una sola volta, la definizione di queste impostazioni di compatibilità deve essere la prima attività eseguita dall'applicazione.  
  
- Aggiungendo la riga seguente [ \<](../configure-apps/file-schema/runtime/runtime-element.md) alla sezione runtime>del file app.config:  
  
    ```xml  
    <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>  
    ```  
  
 Si noti, tuttavia, che il rifiuto esplicito del comportamento non è consigliabile, in quanto rende meno sicura l'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- [Compatibilità tra le versioni](application-compatibility.md)
