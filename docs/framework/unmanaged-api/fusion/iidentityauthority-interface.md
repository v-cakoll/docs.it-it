---
title: Interfaccia IIdentityAuthority
ms.date: 03/30/2017
api_name:
- IIdentityAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IIdentityAuthority
helpviewer_keywords:
- IIdentityAuthority interface [.NET Framework fusion]
ms.assetid: 6277f914-51a8-49be-bec6-52d6d648527d
topic_type:
- apiref
ms.openlocfilehash: 3e2d2335e37ced9139ea44092f10b19566894681
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127087"
---
# <a name="iidentityauthority-interface"></a>Interfaccia IIdentityAuthority

Gestisce chiavi di identità per oggetti di codice.

## <a name="methods"></a>Metodi

|Metodo|Descrizione|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|Ottiene un valore che indica se le due istanze di [IDefinitionIdentity](idefinitionidentity-interface.md) specificate sono uguali.|
|`IIdentityAuthority::AreReferencesEqual`|Ottiene un valore che indica se le due istanze di [IReferenceIdentity](ireferenceidentity-interface.md) specificate sono uguali.|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|Ottiene un valore che indica se le due rappresentazioni di identità della definizione di stringa specificate sono uguali.|
|`IIdentityAuthority::AreTextualReferencesEqual`|Ottiene un valore che indica se le due rappresentazioni di identità di riferimento della stringa specificate sono uguali.|
|`IIdentityAuthority::CreateDefinition`|Ottiene un puntatore a una nuova istanza di `IDefinitionIdentity` che rappresenta l'oggetto di codice nell'ambito corrente.|
|`IIdentityAuthority::CreateReference`|Ottiene un puntatore a una nuova istanza di `IReferenceIdentity` che rappresenta l'oggetto di codice nell'ambito corrente.|
|`IIdentityAuthority::DefinitionToText`|Ottiene una versione in formato stringa del `IDefinitionIdentity`specificato.|
|`IIdentityAuthority::DefinitionToTextBuffer`|Riempie il buffer di caratteri wide specificato con una versione in formato stringa del `IDefinitionIdentity`specificato.|
|`IIdentityAuthority::DoesDefinitionMatchReference`|Ottiene un valore che indica se le istanze di `IDefinitionIdentity` e `IReferenceIdentity` specificate fanno riferimento allo stesso oggetto di codice.|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|Ottiene un valore che indica se le stringhe specificate fanno riferimento allo stesso oggetto di codice.|
|`IIdentityAuthority::GenerateDefinitionKey`|Ottiene un puntatore a una chiave di stringa appena creata per il `IDefinitionIdentity`specificato.|
|`IIdentityAuthority::GenerateReferenceKey`|Ottiene un puntatore a una chiave di stringa appena creata per il `IReferenceIdentity`specificato.|
|`IIdentityAuthority::HashDefinition`|Ottiene un valore hash per il `IDefinitionIdentity`specificato.|
|`IIdentityAuthority::HashReference`|Ottiene un valore hash per il `IReferenceIdentity`specificato.|
|`IIdentityAuthority::ReferenceToText`|Ottiene una versione in formato stringa del `IReferenceIdentity`specificato.|
|`IIdentityAuthority::ReferenceToTextBuffer`|Riempie il buffer di caratteri wide specificato con una versione in formato stringa del `IReferenceIdentity`specificato.|
|`IIdentityAuthority::TextToDefinition`|Ottiene un puntatore a interfaccia a un'istanza `IDefinitionIdentity` generata dalla stringa formattata specificata.|
|`IIdentityAuthority::TextToReference`|Ottiene un puntatore a interfaccia a un'istanza `IReferenceIdentity` generata dalla stringa formattata specificata.|

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

**Intestazione:** Isolation. h

**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfacce Fusion](fusion-interfaces.md)
