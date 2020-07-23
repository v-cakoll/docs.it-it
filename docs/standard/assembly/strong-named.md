---
title: Assembly con nomi sicuri
description: Informazioni sui nomi sicuri per gli assembly .NET che consentono di creare un'identità univoca per un assembly e di impedire conflitti di assembly.
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies, about strong-named assemblies
- assemblies [.NET Framework], strong-named
ms.assetid: d4a80263-f3e0-4d81-9b61-f0cbeae3797b
ms.openlocfilehash: 069e42af6f8d49363d0264c0f6167b4afa3acd61
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925657"
---
# <a name="strong-named-assemblies"></a>Assembly con nomi sicuri

L'assegnazione di un nome sicuro a un assembly permette di creare un'identità univoca e prevenire gli eventuali conflitti con altri assembly.

## <a name="what-makes-a-strong-named-assembly"></a>Come si genera un assembly con nome sicuro?

Per generare un assembly con nome sicuro usare la chiave privata corrispondente alla chiave pubblica distribuita con l'assembly, oltre all'assembly stesso. L'assembly include il relativo manifesto, che a sua volta contiene i nomi e gli hash di tutti i file che costituiscono l'assembly. Gli assembly che hanno lo stesso nome sicuro devono essere uguali.

È possibile assegnare nomi sicuri agli assembly usando Visual Studio o uno strumento da riga di comando. Per altre informazioni, vedere [procedura: firmare un assembly con un nome sicuro](sign-strong-name.md) o un [Sn.exe (strumento nome sicuro)](../../framework/tools/sn-exe-strong-name-tool.md).

Nel creare un assembly con nome sicuro è necessario includere il nome in formato testo semplice dell'assembly, il numero di versione, le informazioni facoltative relative alle impostazioni cultura, una firma digitale e la chiave pubblica corrispondente alla chiave privata usata per apporre la firma.

> [!WARNING]
> Non usare i nomi sicuri per la sicurezza, poiché forniscono solo un'identità univoca.

## <a name="why-strong-name-your-assemblies"></a>Perché assegnare nomi sicuri agli assembly?

Per .NET Framework, gli assembly con nome sicuro sono utili negli scenari seguenti:

- Per abilitare il riferimento agli assembly da parte degli assembly con nome sicuro o per concedere a un `friend` l'accesso all'assembly da altri assembly con nome sicuro.

- Un'app deve accedere a versioni diverse dello stesso assembly. Ciò significa che sono necessarie più versioni di un assembly da caricare affiancate nello stesso dominio di app senza conflitti. Ad esempio , se negli assembly esistono estensioni differenti di una API con lo stesso nome semplice, l'assegnazione di un nome sicuro consente di fornire un'identità univoca a ciascuna versione dell'assembly.

- Non si vuole influire negativamente sulle prestazioni delle app usando il proprio assembly, quindi si usa un assembly indipendente dal dominio. Questo richiede l'uso di nomi sicuri perché gli assembly indipendenti dal dominio devono essere installati in Global Assembly Cache.

- Si vuole centralizzare la manutenzione per l'app applicando i criteri dell'editore, che significa che l'assembly deve essere installato nella Global Assembly Cache.

Per .NET Core, gli assembly con nome sicuro non forniscono vantaggi materiali.

Se si è uno sviluppatore open source e si desiderano i vantaggi di identità di un assembly con nome sicuro per una migliore compatibilità con .NET Framework, provare a archiviare la chiave privata associata a un assembly nel sistema di controllo del codice sorgente.

## <a name="see-also"></a>Vedere anche

- [Assembly Cache globale](../../framework/app-domains/gac.md)
- [Procedura: firmare un assembly con un nome sicuro](sign-strong-name.md)
- [Sn.exe (strumento nome sicuro)](../../framework/tools/sn-exe-strong-name-tool.md)
- [Creare e usare gli assembly con nome sicuro](create-use-strong-named.md)
