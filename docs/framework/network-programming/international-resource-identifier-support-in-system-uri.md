---
title: Supporto per IRI (International Resource Identifier) in System.Uri
ms.date: 03/30/2017
ms.assetid: b5e994c3-3535-4aff-8e1b-b69be22e9a22
ms.openlocfilehash: f78fff250aae177b5f0360e77a1c41a2f2bb0527
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "64647343"
---
# <a name="international-resource-identifier-support-in-systemuri"></a>Supporto per IRI (International Resource Identifier) in System.Uri
La classe <xref:System.Uri?displayProperty=nameWithType> è stata estesa con il supporto per gli IRI (International Resource Identifier) e gli IDN (Internationalized Domain Name). Questi miglioramenti sono disponibili in .NET Framework 3.5, 3.0 SP1 e 2.0 SP1.  
  
## <a name="iri-and-idn-support"></a>Supporto per IRI e IDN  
 Gli indirizzi Web vengono in genere espressi tramite URI (Uniform Resource Identifier), che sono costituiti da un set di caratteri molto limitato:  
  
- Lettere ASCII maiuscole e minuscole dell'alfabeto inglese.  
  
- Cifre comprese tra 0 e 9.  
  
- Numero ridotto di altri simboli ASCII.  
  
 Le specifiche per gli URI sono documentate nelle note RFC 2396 e RFC 3986 pubblicate da Internet Engineering Task Force (IETF).  
  
 Con la crescita di Internet, è sempre più necessario identificare le risorse che usano lingue diverse dall'inglese. Gli identificatori semplificano le operazioni a questo scopo e fanno sì che caratteri non ASCII (caratteri inclusi nel set di caratteri Unicode/ISO 10646) vengano riconosciuti come International Resource Identifier (IRI). Le specifiche per gli IRI sono documentate nella nota RFC 3987, pubblicata da IETF. L'uso di IRI permette a un URL di includere caratteri Unicode.  
  
 La classe <xref:System.Uri?displayProperty=nameWithType> esistente è stata estesa per fornire supporto per gli IRI in base al documento RFC 3987. Gli utenti non noteranno alcun cambiamento dal comportamento di .NET Framework 2.0, a meno che non abilitino in modo specifico gli URI. Questo garantisce la compatibilità delle applicazioni con le versioni precedenti di .NET Framework.  
  
 Un'applicazione può specificare se usare l'analisi degli IDN (Internationalized Domain Name) per i nomi di dominio e se applicare regole di analisi degli IRI. A questo scopo, è possibile usare il file machine.config o il file app.config.  
  
 L'abilitazione degli IDN comporta la conversione di tutte le etichette Unicode in un nome di dominio nei rispettivi equivalenti Punycode. I nomi Punycode contengono solo caratteri ASCII e iniziano sempre con il prefisso "xn--". Questo avviene per supportare i server DNS esistenti in Internet, in quanto la maggior parte dei server DNS supporta solo caratteri ASCII. Vedere il documento RFC 3940.  
  
 L'abilitazione di IRI e IDN influisce sul valore della proprietà <xref:System.Uri.DnsSafeHost%2A?displayProperty=nameWithType>. L'abilitazione di IRI e IDN può anche modificare il comportamento dei metodi <xref:System.Uri.Equals%2A?displayProperty=nameWithType>, <xref:System.Uri.OriginalString%2A?displayProperty=nameWithType>, <xref:System.Uri.GetComponents%2A?displayProperty=nameWithType> e <xref:System.Uri.IsWellFormedOriginalString%2A>.  
  
 La classe <xref:System.GenericUriParser?displayProperty=nameWithType> è stata estesa anche per consentire la creazione di un parser personalizzabile che supporta gli IRI e gli IDN. Il comportamento di un oggetto <xref:System.GenericUriParser?displayProperty=nameWithType> è specificato passando una combinazione bit per bit dei valori disponibili nell'enumerazione <xref:System.GenericUriParserOptions?displayProperty=nameWithType> al costruttore <xref:System.GenericUriParser?displayProperty=nameWithType>. Il tipo <xref:System.GenericUriParserOptions.IriParsing?displayProperty=nameWithType> indica che il parser supporta le regole specificate nel documento RFC 3987 per gli IRI (International Resource Identifier). Gli IRI vengono effettivamente usati solo se sono abilitati.  
  
 Il tipo <xref:System.GenericUriParserOptions.Idn?displayProperty=nameWithType> indica che il parser supporta l'analisi degli IDN (Internationalized Domain Name) dei nomi host. Gli IDN vengono effettivamente usati se sono abilitati.  
  
 L'abilitazione dell'analisi degli URI permette di eseguire la normalizzazione e il controllo dei caratteri in base alle regole IRI più recenti nel documento RFC 3987. Il valore predefinito corrisponde alla disabilitazione dell'analisi degli IRI in modo da eseguire la normalizzazione e il controllo dei caratteri in base ai documenti RFC 2396 e RFC 3986.  
  
 L'elaborazione di IRI e IDN nella classe <xref:System.Uri?displayProperty=nameWithType> può anche essere controllata usando le classi delle impostazioni di configurazione <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType> e <xref:System.Configuration.IdnElement?displayProperty=nameWithType>. L'impostazione <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType> abilita o disabilita l'elaborazione degli IRI nella classe <xref:System.Uri?displayProperty=nameWithType>. L'impostazione <xref:System.Configuration.IdnElement?displayProperty=nameWithType> abilita o disabilita l'elaborazione degli IDN nella classe <xref:System.Uri>. L'impostazione <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType> controlla anche indirettamente gli IDN. L'elaborazione degli IRI deve essere abilitata perché sia possibile elaborare gli IDN. Se l'elaborazione degli IRI è disabilitata, l'elaborazione degli IDN usa l'impostazione predefinita, basata sul comportamento di .NET Framework 2.0 per motivi di compatibilità e i nomi IDN non vengono usati.  
  
 L'impostazione di configurazione per le classi di configurazione <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType> e <xref:System.Configuration.IdnElement?displayProperty=nameWithType> verrà letta una volta quando viene costruita la prima classe <xref:System.Uri?displayProperty=nameWithType>. Le modifiche apportate alle impostazioni di configurazione da questo momento in poi verranno ignorate.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- <xref:System.Uri.DnsSafeHost%2A?displayProperty=nameWithType>
