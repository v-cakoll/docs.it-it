---
title: Sicurezza basata sui ruoli
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- role-based security, about role-based security
- user authentication, principals
- principals [.NET Framework]
- security [.NET Framework], role-based
- permissions [.NET Framework], principals
- authentication [.NET Framework], principals
- role-based security, principals
ms.assetid: 578cc32b-5654-4d8b-9d8c-ebcbc5c75390
ms.openlocfilehash: 8986e778e84fdf211d11fd7a897508acc7412207
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291201"
---
# <a name="role-based-security"></a>Sicurezza basata sui ruoli
I ruoli vengono spesso usati nelle applicazioni finanziarie o aziendali per l'applicazione dei criteri di sicurezza. Ad esempio, è possibile che un'applicazione imponga limiti alle dimensioni della transazione in corso di elaborazione in funzione del ruolo rivestito dall'utente che effettua la richiesta. Gli impiegati potrebbero essere autorizzati a elaborare unicamente transazioni inferiori a una determinata soglia, mentre per i supervisori il limite potrebbe essere superiore e per i vicepresidenti ancora più alto (o addirittura assente). La sicurezza basata sui ruoli può anche essere usata quando un'applicazione richiede più approvazioni per completare un'operazione. È questo ad esempio il caso di un sistema di acquisto in cui qualsiasi dipendente può generare una richiesta di acquisto, ma solo un agente di acquisto può convertire la richiesta in un ordine di acquisto da inviare a un fornitore.  
  
 La sicurezza basata sui ruoli di .NET Framework supporta l'autorizzazione rendendo disponibili al thread corrente informazioni sull'entità, costruita da un'identità associata. L'identità (e il principale che contribuisce a definire) può essere basata su un account Windows o essere un'identità personalizzata non correlata ad alcun account Windows. Le applicazioni .NET Framework possono decidere in merito all'autorizzazione sulla base dell'identità del principale, dell'appartenenza a un ruolo o di entrambi i fattori. Un ruolo è un set denominato di principali che dispongono degli stessi privilegi relativamente alla sicurezza (ad esempio un cassiere o un direttore). Un principale può essere membro di uno o più ruoli. Le applicazioni possono pertanto usare l'appartenenza ai ruoli per determinare se un principale è autorizzato a eseguire un'operazione richiesta.  
  
 Per garantire facilità d'uso e coerenza con la sicurezza dall'accesso di codice, la sicurezza basata sui ruoli di .NET Framework fornisce oggetti <xref:System.Security.Permissions.PrincipalPermission?displayProperty=nameWithType> che consentono a Common Language Runtime di eseguire l'autorizzazione in modo analogo ai controlli di sicurezza dall'accesso di codice. La classe <xref:System.Security.Permissions.PrincipalPermission> rappresenta l'identità o il ruolo a cui il principale deve corrispondere ed è compatibile sia con i controlli di sicurezza dichiarativi che con quelli imperativi. È anche possibile accedere direttamente alle informazioni sull'identità di un principale ed eseguire controlli di ruolo e di identità nel codice quando necessario.  
  
 .NET Framework fornisce un supporto della sicurezza basata sui ruoli sufficientemente flessibile ed estendibile da rispondere alle esigenze di un'ampia gamma di applicazioni. Si può scegliere di interagire con infrastrutture di sicurezza esistenti, quali i servizi di COM+ 1.0, oppure creare un sistema di autenticazione personalizzato. La sicurezza basata sui ruoli è particolarmente adatta all'uso nelle applicazioni Web ASP.NET, che vengono elaborate principalmente sul server. La sicurezza basata sui ruoli di .NET Framework può tuttavia essere usata sia su client che su server.  
  
 Prima di leggere questa sezione, assicurarsi di comprendere il materiale presentato nei [concetti chiave relativi alla sicurezza](key-security-concepts.md).  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[Oggetti Principal e Identity](principal-and-identity-objects.md)|Illustra come configurare e gestire identità e principali sia Windows che generici.|  
|[Concetti principali sulla sicurezza](key-security-concepts.md)|Introduce i concetti fondamentali che è necessario comprendere prima di affrontare il tema della sicurezza di NET Framework.|  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.Security.Permissions.PrincipalPermission?displayProperty=nameWithType>
