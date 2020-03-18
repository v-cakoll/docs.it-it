---
title: Concetti principali sulla sicurezza
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- unauthorized access
- permissions [.NET Framework]
- security [.NET Framework], about security
ms.assetid: 3cfced4f-ea02-4e66-ae98-d69286363e98
ms.openlocfilehash: b7bcb7e56ca14d129eadcaeac19452d4a443713d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400659"
---
# <a name="key-security-concepts"></a>Concetti principali sulla sicurezza
Microsoft .NET Framework offre la sicurezza basata sui ruoli per risolvere i problemi di sicurezza relativi al codice mobile e per fornire un supporto che consenta di abilitare i componenti per determinare le operazioni per cui gli utenti dispongono di autorizzazioni.  
  
## <a name="type-safety-and-security"></a>Indipendenza dai tipi e sicurezza  
 Il codice indipendente dai tipi accede solo alle posizioni di memoria per le quali dispone di autorizzazioni. (Per questa discussione, l'indipendenza dai tipi si riferisce specificamente all'indipendenza dai tipi di memoria e non deve essere confusa con l'indipendenza dai tipi in modo più ampio. Ad esempio, il codice indipendente dai tipi non può leggere i valori dai campi privati di un altro oggetto. Accede ai tipi solo in modalità ben definite e consentite.  
  
 Durante la compilazione Just-In-Time (JIT), un processo di verifica facoltativo esamina i metadati e MSIL (Microsoft Intermediate Language) di un metodo su cui eseguire la compilazione JIT in codice macchina nativo per verificare che siano indipendenti dai tipi. Questo processo viene ignorato se il codice dispone dell'autorizzazione per ignorare la verifica. Per altre informazioni sulla verifica, vedere [Processo di esecuzione gestita](../../../docs/standard/managed-execution-process.md).  
  
 Sebbene la verifica dell'indipendenza dai tipi non sia obbligatoria per l'esecuzione di codice gestito, l'indipendenza dai tipi ha un ruolo fondamentale nell'imposizione della sicurezza e nell'isolamento dell'assembly. Quando il codice è indipendente dai tipi, Common Language Runtime può isolare completamente i singoli assembly. Questo isolamento contribuisce a garantire che gli assembly non interferiscano tra loro, aumentando l'affidabilità dell'applicazione. I componenti indipendenti dai tipi possono essere eseguiti in modo sicuro nello stesso processo anche se sono attendibili a livelli diversi. Quando il codice non è indipendente dai tipi possono verificarsi effetti collaterali indesiderati. Il runtime, ad esempio, non è in grado di impedire al codice gestito di effettuare chiamate a codice nativo (non gestito) e di eseguire operazioni dannose. Quando il codice è indipendente dai tipi, il meccanismo di imposizione della sicurezza del runtime ne impedisce l'accesso al codice nativo a meno che non disponga delle autorizzazioni. Per essere eseguito, tutto il codice non indipendente dai tipi deve aver ottenuto <xref:System.Security.Permissions.SecurityPermission> con il membro di enumerazione passato <xref:System.Security.Permissions.SecurityPermissionAttribute.SkipVerification%2A>.  
  
 Per altre informazioni, vedere [Code Access Security Basics](../../../docs/framework/misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice).  
  
## <a name="principal"></a>Server principale  
 Un'entità rappresenta l'identità e il ruolo di un utente e agisce per conto dell'utente. La sicurezza basata sui ruoli in .NET Framework supporta tre tipi di entità:  
  
- Le entità generiche rappresentano utenti e ruoli che esistono indipendentemente dai ruoli e dagli utenti di Windows.  
  
- Le entità di Windows rappresentano gli utenti di Windows e i relativi ruoli (o i gruppi di Windows). Un'entità di Windows può rappresentare un altro utente, il che significa che l'entità può accedere a una risorsa per conto dell'utente presentando l'identità appartenente a tale utente.  
  
- Le entità personalizzate possono essere definite da un'applicazione secondo le modalità richieste dalla specifica applicazione. Possono estendere la nozione di base di identità e di ruoli dell'entità.  
  
 Per altre informazioni, vedere [Oggetti Principal e Identity](../../../docs/standard/security/principal-and-identity-objects.md).  
  
## <a name="authentication"></a>Authentication  
 L'autenticazione è il processo di individuazione e verifica dell'identità di un'entità eseguito esaminando e convalidando le credenziali dell'utente rispetto a un'autorità specificata. Le informazioni ottenute durante l'autenticazione possono essere usate direttamente dal codice. È anche possibile usare la sicurezza basata sui ruoli di .NET Framework per autenticare l'utente corrente e per determinare se consentire a tale entità di accedere al codice. Vedere gli overload del metodo <xref:System.Security.Principal.WindowsPrincipal.IsInRole%2A?displayProperty=nameWithType> per esempi su come autenticare l'entità per ruoli specifici. Ad esempio, è possibile usare l'overload <xref:System.Security.Principal.WindowsPrincipal.IsInRole%28System.String%29?displayProperty=nameWithType> per determinare se l'utente corrente è un membro del gruppo Administrators.  
  
 Un'ampia gamma di meccanismi di autenticazione usati oggi, molti dei quali possono essere usati con la sicurezza basata sui ruoli di .NET Framework. Alcuni dei meccanismi più diffusi sono il meccanismo di base, il digest, il Passport, il sistema operativo (ad esempio NTLM o Kerberos) o i meccanismi definiti dall'applicazione.  
  
### <a name="example"></a>Esempio  
 L'esempio seguente richiede che l'entità attiva sia un amministratore. Il parametro `name` è `null`, che consente a qualsiasi utente con ruolo di amministratore di passare la richiesta.  
  
> [!NOTE]
> In Windows Vista, 	la funzionalità Controllo dell'account utente determina i privilegi di un utente. Ai membri del gruppo Administrators predefinito vengono assegnati due token di accesso in fase di esecuzione, ovvero un token di accesso utente standard e un token di accesso amministratore. Per impostazione predefinita, viene assegnato il ruolo dell'utente standard. Per eseguire il codice che richiede un ruolo da amministratore è necessario elevare i privilegi da utente standard ad amministratore. È possibile farlo quando si avvia un'applicazione facendo clic con il pulsante destro del mouse sull'icona dell'applicazione e indicando l'opzione di esecuzione come amministratore.  
  
 [!code-cpp[Classic PrincipalPermission Example#1](../../../samples/snippets/cpp/VS_Snippets_CLR_Classic/classic PrincipalPermission Example/CPP/source.cpp#1)]
 [!code-csharp[Classic PrincipalPermission Example#1](../../../samples/snippets/csharp/VS_Snippets_CLR_Classic/classic PrincipalPermission Example/CS/source.cs#1)]
 [!code-vb[Classic PrincipalPermission Example#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_Classic/classic PrincipalPermission Example/VB/source.vb#1)]  
  
 L'esempio seguente mostra come determinare l'identità dell'entità e i ruoli disponibili per l'entità. Un'applicazione di questo esempio potrebbe essere la conferma che l'utente corrente ha un ruolo autorizzato all'uso dell'applicazione.  
  
 [!code-cpp[System.Security.Principal.WindowsBuiltInRole Example#1](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Security.Principal.WindowsBuiltInRole Example/CPP/source.cpp#1)]
 [!code-csharp[System.Security.Principal.WindowsBuiltInRole Example#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Security.Principal.WindowsBuiltInRole Example/CS/source.cs#1)]
 [!code-vb[System.Security.Principal.WindowsBuiltInRole Example#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Security.Principal.WindowsBuiltInRole Example/VB/source.vb#1)]  
  
## <a name="authorization"></a>Autorizzazione  
 L'autorizzazione è il processo che consente di determinare se un'entità è autorizzata a eseguire un'azione richiesta. L'autorizzazione si verifica dopo l'autenticazione e usa le informazioni di identità e i ruoli dell'entità per determinare a quali risorse può accedere. È possibile usare la sicurezza basata sui ruoli di .NET Framework per implementare l'autorizzazione.
