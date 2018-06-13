---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 14150a992130e9ed4734c950d4ed92f1bbd3206c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485557"
---
# <a name="mustunderstandbehavior"></a>MustUnderstandBehavior
MustUnderstandBehavior  
  
## <a name="syntax"></a>Sintassi  
  
```  
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe MustUnderstandBehavior non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe MustUnderstandBehavior dispone della proprietà seguente:  
  
### <a name="validatemustunderstand"></a>ValidateMustUnderstand  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Se `true`, tutte le intestazioni SOAP con l'attributo `MustUnderstand` non gestite determinano la generazione di un'eccezione.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Description.MustUnderstandBehavior>
