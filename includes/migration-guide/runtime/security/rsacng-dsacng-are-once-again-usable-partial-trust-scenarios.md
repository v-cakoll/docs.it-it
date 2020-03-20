---
ms.openlocfilehash: 8b41e3234c00059ecb5088bbf2597611d7f139b8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857258"
---
### <a name="rsacng-and-dsacng-are-once-again-usable-in-partial-trust-scenarios"></a>RSACng e DSACng possono essere di nuovo usati in scenari di attendibilità parziale

|   |   |
|---|---|
|Dettagli|In alcuni casi, CngLightup (usato in diverse API di crittografia di livello superiore, ad esempio <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType>) e <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> si basano sull'attendibilità totale. Questi casi includono i P/Invoke senza l'asserzione delle autorizzazioni <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType> e i percorsi di codice in cui <xref:System.Security.Cryptography.CngKey?displayProperty=nameWithType> include richieste di autorizzazione per <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType>. A partire da .NET Framework 4.6.2, CngLightup viene usato per passare a <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType>, quando possibile. Di conseguenza, le app con attendibilità parziale che usano <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType> hanno iniziato a restituire errori e a generare eccezioni <xref:System.Security.SecurityException>. Questa modifica aggiunge le asserzioni necessarie in modo che tutte le funzioni che usano CngLightup abbiano le autorizzazioni richieste.|
|Suggerimento|Se questa modifica apportata in .NET Framework 4.6.2 ha avuto un impatto negativo sulle app con attendibilità parziale, eseguire l'aggiornamento a .NET Framework 4.7.1.|
|Scope|Microsoft Edge|
|Versione|4.6.2|
|Type|Runtime|
|API interessate|<ul><li><xref:System.Security.Cryptography.DSACng.%23ctor(System.Security.Cryptography.CngKey)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.Key?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.LegalKeySizes?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.CreateSignature(System.Byte[])?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.DSACng.VerifySignature(System.Byte[],System.Byte[])?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.%23ctor(System.Security.Cryptography.CngKey)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.Key?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.Decrypt(System.Byte[],System.Security.Cryptography.RSAEncryptionPadding)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.SignHash(System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|
