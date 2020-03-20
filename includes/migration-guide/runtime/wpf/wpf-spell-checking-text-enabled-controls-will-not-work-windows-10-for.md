---
ms.openlocfilehash: abb89099c4c8a5d9c0e55ef8f357faf44e75b045
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858655"
---
### <a name="wpf-spell-checking-in-text-enabled-controls-will-not-work-in-windows-10-for-languages-not-in-the-oss-input-language-list"></a>Il controllo ortografico WPF nei controlli con supporto di testo non funziona in Windows 10 per le lingue non incluse nell'elenco lingue di input del sistema operativo

|   |   |
|---|---|
|Dettagli|Durante l'esecuzione in Windows 10, il controllo ortografico potrebbe non funzionare per i controlli WPF basati su testo perché le funzionalità di controllo ortografico della piattaforma sono disponibili solo per le lingue presenti nell'elenco delle lingue di input. In Windows 10, quando una lingua viene aggiunta all'elenco di tastiere disponibili, Windows scarica e installa automaticamente una funzione corrispondente nel pacchetto di funzionalità su richiesta (FOD, Feature on Demand) che offre funzionalità di controllo ortografico. Aggiungendo la lingua all'elenco di lingue di input, il controllo ortografico sarà supportato.|
|Suggerimento|Tenere presente che per il funzionamento del controllo ortografico in Windows 10 è necessario aggiungere la lingua o il testo da sottoporre a controllo come lingua di input.|
|Scope|Microsoft Edge|
|Versione|4.6|
|Type|Runtime|
