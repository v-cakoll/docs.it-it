---
title: Gestori di token personalizzati
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5062669f-8bfc-420a-a25d-d8ab992ab10e
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 56fb7fcb162025ec05bc1171cb137d445c4dfee5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="custom-token-handlers"></a><span data-ttu-id="0cd97-102">Gestori di token personalizzati</span><span class="sxs-lookup"><span data-stu-id="0cd97-102">Custom Token Handlers</span></span>
<span data-ttu-id="0cd97-103">Questo argomento illustra i gestori di token in WIF e ne descrive l'uso per l'elaborazione dei token.</span><span class="sxs-lookup"><span data-stu-id="0cd97-103">This topic discusses token handlers in WIF and how they are used to process tokens.</span></span> <span data-ttu-id="0cd97-104">L'argomento spiega anche cosa serve per creare gestori di token personalizzati per i tipi di token non supportati per impostazione predefinita in WIF.</span><span class="sxs-lookup"><span data-stu-id="0cd97-104">The topic also covers what is necessary to create custom token handlers for token types that are not supported by default in WIF.</span></span>  
  
## <a name="introduction-to-token-handlers-in-wif"></a><span data-ttu-id="0cd97-105">Introduzione ai gestori di Token di WIF</span><span class="sxs-lookup"><span data-stu-id="0cd97-105">Introduction to Token Handlers in WIF</span></span>  
 <span data-ttu-id="0cd97-106">WIF si basa sui gestori di token di sicurezza per creare, leggere, scrivere e convalidare i token per un'applicazione relying party (RP) o un servizio token di sicurezza (STS).</span><span class="sxs-lookup"><span data-stu-id="0cd97-106">WIF relies on security token handlers to create, read, write, and validate tokens for a relying party (RP) application or a security token service (STS).</span></span> <span data-ttu-id="0cd97-107">I gestori di token sono punti di estendibilità che consentono di aggiungere un gestore di token personalizzato nella pipeline WIF o di personalizzare il modo in cui un gestore di token esistente gestisce i token.</span><span class="sxs-lookup"><span data-stu-id="0cd97-107">Token handlers are extensibility points for you to add a custom token handler in the WIF pipeline, or to customize the way that an existing token handler manages tokens.</span></span> <span data-ttu-id="0cd97-108">WIF offre nove gestori di token di sicurezza predefiniti che possono essere modificati o sottoposti interamente a override per modificare le funzionalità in base alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="0cd97-108">WIF provides nine built-in security token handlers that can be modified or entirely overridden to change the functionality as necessary.</span></span>  
  
## <a name="built-in-security-token-handlers-in-wif"></a><span data-ttu-id="0cd97-109">Gestori di token di sicurezza predefiniti in WIF</span><span class="sxs-lookup"><span data-stu-id="0cd97-109">Built-In Security Token Handlers in WIF</span></span>  
 <span data-ttu-id="0cd97-110">WIF 4.5 include nove classi di gestori di token di sicurezza che derivano dalla classe di base astratta <xref:System.IdentityModel.Tokens.SecurityTokenHandler>:</span><span class="sxs-lookup"><span data-stu-id="0cd97-110">WIF 4.5 includes nine security token handler classes that derive from the abstract base class <xref:System.IdentityModel.Tokens.SecurityTokenHandler>:</span></span>  
  
-   <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.UserNameSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>  
  
## <a name="adding-a-custom-token-handler"></a><span data-ttu-id="0cd97-111">Aggiunta di un gestore di token personalizzato</span><span class="sxs-lookup"><span data-stu-id="0cd97-111">Adding a Custom Token Handler</span></span>  
 <span data-ttu-id="0cd97-112">Per alcuni tipi di token, ad esempio i token SWT (Simple Web Token) e JWT (JSON Web Token) non esistono gestori di token predefiniti forniti da WIF.</span><span class="sxs-lookup"><span data-stu-id="0cd97-112">Some token types, such as Simple Web Tokens (SWT) and JSON Web Tokens (JWT) do not have built-in token handlers provided by WIF.</span></span> <span data-ttu-id="0cd97-113">Per creare gestori di token personalizzati per questi e per altri tipi di token che non dispongono di un gestore predefinito, è necessario eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="0cd97-113">For these token types and for others that do not have a built-in handler, you need to perform the following steps to create a custom token handler.</span></span>  
  
#### <a name="adding-a-custom-token-handler"></a><span data-ttu-id="0cd97-114">Aggiunta di un gestore di token personalizzato</span><span class="sxs-lookup"><span data-stu-id="0cd97-114">Adding a custom token handler</span></span>  
  
1.  <span data-ttu-id="0cd97-115">Creare una nuova classe che derivi da <xref:System.IdentityModel.Tokens.SecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="0cd97-115">Create a new class that derives from <xref:System.IdentityModel.Tokens.SecurityTokenHandler>.</span></span>  
  
2.  <span data-ttu-id="0cd97-116">Eseguire l'override dei metodi seguenti fornendo un'implementazione personalizzata:</span><span class="sxs-lookup"><span data-stu-id="0cd97-116">Override the following methods and provide your own implementation:</span></span>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanReadToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ReadToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanWriteToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.WriteToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanValidateToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>  
  
3.  <span data-ttu-id="0cd97-117">Aggiungere un riferimento al nuovo gestore di token personalizzato nella sezione  **\<system.identityModel>** relativa a WIF del file *Web.config* o *App.config*.</span><span class="sxs-lookup"><span data-stu-id="0cd97-117">Add a reference to the new custom token handler in the *Web.config* or *App.config* file, within the **\<system.identityModel>** section that applies to WIF.</span></span> <span data-ttu-id="0cd97-118">Il markup di configurazione seguente, ad esempio, specifica un nuovo gestore di token denominato **MyCustomTokenHandler** che risiede nello spazio dei nomi **CustomToken**.</span><span class="sxs-lookup"><span data-stu-id="0cd97-118">For example, the following configuration markup specifies a new token handler named **MyCustomTokenHandler** that resides in the **CustomToken** namespace.</span></span>  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```  
  
     <span data-ttu-id="0cd97-119">Si noti che se si specifica un gestore di token personalizzato per la gestione di un tipo di token già dotato di un gestore di token predefinito, è necessario aggiungere un elemento  **\<remove>** per rilasciare il gestore predefinito e usare il gestore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0cd97-119">Note that if you are providing your own token handler to handle a token type that already has a built-in token handler, you need to add a **\<remove>** element to drop the default handler and use your custom handler instead.</span></span> <span data-ttu-id="0cd97-120">La configurazione seguente, ad esempio, sostituisce il gestore <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> predefinito con il gestore di token personalizzato:</span><span class="sxs-lookup"><span data-stu-id="0cd97-120">For example, the following configuration replaces the default <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> with the custom token handler:</span></span>  
  
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
