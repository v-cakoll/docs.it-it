---
title: È stato creato un riferimento all'assembly di interoperabilità incorporato '<assembly1>' a causa di un riferimento indiretto a tale assembly dall'assembly '<assembly2>'
ms.date: 07/20/2015
f1_keywords:
- vbc40059
- bc40059
helpviewer_keywords:
- VBC40059
- BC40059
ms.assetid: 520e39cb-8ab6-46f5-aa00-08afd51b4b7c
ms.openlocfilehash: 36ae9d8257c8265b813bba446f685428bbf0b1e7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64646901"
---
# <a name="a-reference-was-created-to-embedded-interop-assembly-assembly1-because-of-an-indirect-reference-to-that-assembly-from-assembly-assembly2"></a>È stato creato un riferimento all'assembly di interoperabilità incorporato '\<assembly1 >' a causa di un riferimento indiretto a tale assembly dall'assembly '\<assembly2 >'
È stato creato un riferimento all'assembly di interoperabilità incorporato '\<assembly1>' a causa di un riferimento indiretto a tale assembly creato dall'assembly '\<assembly2>'. Provare a modificare la proprietà 'Incorpora tipi di interoperabilità' in un assembly.  
  
 È stato aggiunto un riferimento a un assembly (assembly1) con la proprietà `Embed Interop Types` impostata su `True`. Si dà così istruzione al compilatore di incorporare le informazioni sui tipi di interoperabilità da tale assembly. Il compilatore non può tuttavia incorporare le informazioni sui tipi di interoperabilità da tale assembly perché anche un altro assembly a cui si fa riferimento (assembly2) fa riferimento a tale assembly (assembly1) e ha la proprietà `Embed Interop Types` impostata su `False`.  
  
> [!NOTE]
>  L'impostazione della proprietà `Embed Interop Types` per un riferimento a un assembly su `True` equivale a fare riferimento all'assembly usando l'opzione del compilatore della riga di comando `/link`.  
  
 **ID errore:** BC40059  
  
### <a name="to-address-this-warning"></a>Per risolvere questo avviso  
  
- Per incorporare le informazioni sui tipi di interoperabilità per entrambi gli assembly, impostare la proprietà `Embed Interop Types` per tutti i riferimenti a assembly1 su `True`.  
  
- Per rimuovere l'avviso, è possibile impostare la proprietà `Embed Interop Types` di assembly1 su `False`. In questo caso, le informazioni sul tipo di interoperabilità viene forniti da un assembly di interoperabilità primario (PIA).  
  
## <a name="see-also"></a>Vedere anche

- [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md)
- [Interoperabilità con codice non gestito](../../../framework/interop/index.md)
