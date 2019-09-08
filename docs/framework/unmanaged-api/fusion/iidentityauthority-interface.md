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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7421e0d0e1a1f0e1a5fbe0d0eb7d5a0ab2a48b9a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796418"
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
|`IIdentityAuthority::CreateDefinition`|Ottiene un puntatore a una nuova `IDefinitionIdentity` istanza di che rappresenta l'oggetto di codice nell'ambito corrente.|
|`IIdentityAuthority::CreateReference`|Ottiene un puntatore a una nuova `IReferenceIdentity` istanza di che rappresenta l'oggetto di codice nell'ambito corrente.|
|`IIdentityAuthority::DefinitionToText`|Ottiene una versione in formato stringa dell'oggetto `IDefinitionIdentity`specificato.|
|`IIdentityAuthority::DefinitionToTextBuffer`|Riempie il buffer di caratteri wide specificato con una versione in formato stringa `IDefinitionIdentity`dell'oggetto specificato.|
|`IIdentityAuthority::DoesDefinitionMatchReference`|Ottiene un valore che indica se le istanze `IDefinitionIdentity` e `IReferenceIdentity` specificate fanno riferimento allo stesso oggetto di codice.|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|Ottiene un valore che indica se le stringhe specificate fanno riferimento allo stesso oggetto di codice.|
|`IIdentityAuthority::GenerateDefinitionKey`|Ottiene un puntatore a una chiave di stringa appena creata per l' `IDefinitionIdentity`oggetto specificato.|
|`IIdentityAuthority::GenerateReferenceKey`|Ottiene un puntatore a una chiave di stringa appena creata per l' `IReferenceIdentity`oggetto specificato.|
|`IIdentityAuthority::HashDefinition`|Ottiene un valore hash per l'oggetto `IDefinitionIdentity`specificato.|
|`IIdentityAuthority::HashReference`|Ottiene un valore hash per l'oggetto `IReferenceIdentity`specificato.|
|`IIdentityAuthority::ReferenceToText`|Ottiene una versione in formato stringa dell'oggetto `IReferenceIdentity`specificato.|
|`IIdentityAuthority::ReferenceToTextBuffer`|Riempie il buffer di caratteri wide specificato con una versione in formato stringa `IReferenceIdentity`dell'oggetto specificato.|
|`IIdentityAuthority::TextToDefinition`|Ottiene un puntatore a interfaccia a `IDefinitionIdentity` un'istanza generata dalla stringa formattata specificata.|
|`IIdentityAuthority::TextToReference`|Ottiene un puntatore a interfaccia a `IReferenceIdentity` un'istanza generata dalla stringa formattata specificata.|

## <a name="requirements"></a>Requisiti

**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).

**Intestazione:** Isolation. h

**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfacce Fusion](fusion-interfaces.md)
