---
ms.openlocfilehash: 9678c077e278a9d76ffd5c2ce10e63ebe3ad09f7
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2019
ms.locfileid: "68235595"
---
### <a name="x509certificateclaimsetfindclaims-considers-all-claimtypes"></a>X509CertificateClaimSet.FindClaims considera tutti gli argomenti claimType

|   |   |
|---|---|
|Dettagli|Nelle app destinate a .NET Framework 4.6.1, se un set di attestazioni X509 viene inizializzato da un certificato con più voci DNS nel proprio campo SAN, il metodo <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=name> cerca di stabilire una corrispondenza con l'argomento claimType con tutte le voci DNS. Per le app destinate a versioni precedenti di .NET Framework, il metodo <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=name> tenta di stabilire una corrispondenza con l'argomento claimType solo con l'ultima voce DNS.|
|Suggerimento|Questa modifica riguarda solo le applicazioni destinate a .NET Framework 4.6.1. Questa modifica potrebbe essere disabilitata (o abilitata se la destinazione è una versione precedente alla 4.6.1) con l'opzione di compatibilità [DisableMultipleDNSEntries](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md#mitigation).|
|Ambito|Secondario|
|Versione|4.6.1|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims(System.String,System.String)?displayProperty=nameWithType></li></ul>|
