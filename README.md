# Combo Bizurado Digital — PMPE

Página de venda do combo (Resumo Bizurado + Caderno Tático de Questões + Vade Mecum
Tático), lançada com o edital da PMPE. É um clone da página do Resumo Bizurado
(`C:\Projetos\cppem\Venda Direta CPPEM\apostila`): mesma paleta, mesmo tracking,
mesmo exit popup. O que vale lá (tracking, mobile, publicação na Vercel) vale aqui.

**Fluxo:** clique no CTA → checkout direto, sem formulário.

## O que muda em relação ao resumo

| | Valor |
|---|---|
| Checkout | `https://checkout.cppem.com.br/pay/combo-bizurado-pmpe-digital` |
| Preço | De R$ 189,00 por R$ 139,90 (-26%) |
| `utm_campaign` de fallback | `combo_pmpe` |
| Evento `iniciar_checkout` | `produto: combo_bizurado_pmpe`, `valor: 139.9` |
| Chave de origem no storage | `cppem_origem_combo` |
| Exit popup | `prefix: cppem_combo`, `origem: exit_popup_combo_pmpe` (mesma aba `APOSTILA_COMUNIDADE`) |

O botão do hero mantém o id `IPEyzyfmJhKQEYIXAlZH` da regra de clique da PixelX.
Se a regra no painel estiver presa ao domínio do resumo, precisa ser liberada para
o domínio do combo, senão a conversão não conta.

## Assets

- `combo.webp`: os três tablets em leque, fundo transparente (hero e oferta)
- `combo-resumo.webp`, `combo-questoes.webp`, `combo-vade.webp`: capas 400×500 dos cards
- `og-combo.jpg`: 1200×630 para compartilhamento

Gerados a partir dos mockups originais de 1024px (Caderno e Vade) e do `apostila.webp`
do resumo.

## Checklist antes do disparo

- [ ] Parcelamento conferido no checkout (a página diz só "até 12x", sem valor de parcela)
- [ ] Checkout abriu com UTMs e `external_id`
- [ ] Regra de clique da PixelX disparando neste domínio
- [ ] Popup de saída testado com `ExitPopup.show()`
