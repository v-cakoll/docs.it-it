---
title: Gestori di token personalizzati
ms.date: 03/30/2017
ms.assetid: 5062669f-8bfc-420a-a25d-d8ab992ab10e
author: BrucePerlerMS
ms.openlocfilehash: f7d611bf396f028ff23a39cd529825f99fec300a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650423"
---
# <a name="custom-token-handlers"></a>Gestori di token personalizzati
Questo argomento illustra i gestori di token in WIF e ne descrive l'uso per l'elaborazione dei token. L'argomento spiega anche cosa serve per creare gestori di token personalizzati per i tipi di token non supportati per impostazione predefinita in WIF.  
  
## <a name="introduction-to-token-handlers-in-wif"></a>Introduzione ai gestori di Token di WIF  
 WIF si basa sui gestori di token di sicurezza per creare, leggere, scrivere e convalidare i token per un'applicazione relying party (RP) o un servizio token di sicurezza (STS). I gestori di token sono punti di estendibilità che consentono di aggiungere un gestore di token personalizzato nella pipeline WIF o di personalizzare il modo in cui un gestore di token esistente gestisce i token. WIF offre nove gestori di token di sicurezza predefiniti che possono essere modificati o sottoposti interamente a override per modificare le funzionalità in base alle proprie esigenze.  
  
## <a name="built-in-security-token-handlers-in-wif"></a>Gestori di token di sicurezza predefiniti in WIF  
 WIF 4.5 include nove classi di gestori di token di sicurezza che derivano dalla classe di base astratta <xref:System.IdentityModel.Tokens.SecurityTokenHandler>:  
  
- <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.UserNameSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>  
  
## <a name="adding-a-custom-token-handler"></a>Aggiunta di un gestore di token personalizzato  
 Per alcuni tipi di token, ad esempio i token SWT (Simple Web Token) e JWT (JSON Web Token) non esistono gestori di token predefiniti forniti da WIF. Per creare gestori di token personalizzati per questi e per altri tipi di token che non dispongono di un gestore predefinito, è necessario eseguire la procedura seguente.  
  
#### <a name="adding-a-custom-token-handler"></a>Aggiunta di un gestore di token personalizzato  
  
1. Creare una nuova classe che derivi da <xref:System.IdentityModel.Tokens.SecurityTokenHandler>.  
  
2. Eseguire l'override dei metodi seguenti fornendo un'implementazione personalizzata:  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanReadToken%2A>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ReadToken%2A>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanWriteToken%2A>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.WriteToken%2A>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanValidateToken%2A>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>  
  
3. Aggiungere un riferimento al nuovo gestore di token personalizzato nella sezione  **\<system.identityModel>** relativa a WIF del file *Web.config* o *App.config*. Il markup di configurazione seguente, ad esempio, specifica un nuovo gestore di token denominato **MyCustomTokenHandler** che risiede nello spazio dei nomi **CustomToken**.  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```  
  
     Si noti che se si specifica un gestore di token personalizzato per la gestione di un tipo di token già dotato di un gestore di token predefinito, è necessario aggiungere un elemento  **\<remove>** per rilasciare il gestore predefinito e usare il gestore personalizzato. La configurazione seguente, ad esempio, sostituisce il gestore <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> predefinito con il gestore di token personalizzato:  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <remove type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=abcdefg123456789">  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```
