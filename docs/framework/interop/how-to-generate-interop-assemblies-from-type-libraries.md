---
title: 'Procedura: generare assembly di interoperabilità da librerie dei tipi'
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- Type Library Importer
- type libraries
- COM interop, importing type library
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62d9213e58aaabd0b4001d5c6a7fd6fd375eba2e
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874858"
---
# <a name="how-to-generate-interop-assemblies-from-type-libraries"></a>Procedura: generare assembly di interoperabilità da librerie dei tipi
[Tlbimp.exe (utilità di importazione della libreria dei tipi)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) è uno strumento da riga di comando che converte in metadati le coclassi e le interfacce contenute in una libreria dei tipi COM. Questo strumento crea automaticamente un assembly di interoperabilità e lo spazio dei nomi per le informazioni sui tipi. Dopo che i metadati di una classe sono disponibili, i client gestiti possono creare istanze del tipo COM e chiamarne i metodi, come se si trattasse di un'istanza di .NET. Tlbimp.exe converte un'intera libreria dei tipi in metadati in una sola operazione e non può generare informazioni sui tipi per un subset dei tipi definiti in una libreria dei tipi.  
  
### <a name="to-generate-an-interop-assembly-from-a-type-library"></a>Per generare un assembly di interoperabilità da una libreria dei tipi  
  
1.  Utilizzare il seguente comando:  
  
     **tlbimp** \<*file-libreria-tipi*>  
  
     L'aggiunta dell'opzione **/out:** produce un assembly di interoperabilità con un nome modificato, ad esempio LOANLib.dll. La modifica del nome di assembly di interoperabilità può essere utile per distinguerlo dalla DLL COM originale e impedire che si verifichino problemi a causa di nomi duplicati.  
  
## <a name="example"></a>Esempio  
 Il comando seguente produce l'assembly Loanlib.dll nello spazio dei nomi `Loanlib`.  
  
```  
tlbimp Loanlib.tlb  
```  
  
 Il comando seguente produce un assembly di interoperabilità con un nome modificato (LOANLib.dll).  
  
```  
tlbimp LoanLib.tlb /out: LOANLib.dll  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Importazione di una libreria dei tipi come assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)  
 [Esposizione di componenti COM a .NET Framework](../../../docs/framework/interop/exposing-com-components.md)
