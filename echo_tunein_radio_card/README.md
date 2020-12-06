# Echo tunein radio card

*Please :star: this repo if you find it useful*

Lovelace card with pre-defined Israel radio station buttons to play on Amazon echo device from [Tunein](https://tunein.com/) streaming service.

## Prerequisites

- [Mini media player](https://github.com/kalkih/mini-media-player)
- [Decluttering card](https://github.com/custom-cards/decluttering-card)
- [Alexa media player](https://github.com/custom-components/alexa_media_player)

## Scripts

```yaml
script:
  media_player_play_tunein_radio:
    sequence:
      - service: media_player.play_media
        data_template:
          entity_id: "{{ entity_id }}"
          media_content_id: "{{ content_id }}"
          media_content_type: TUNEIN
```

## Templates

Media player card template with pre deffined Tunein israel radio stations.

```yaml
decluttering_templates:
  template_media_player_echo:
    card:
      type: custom:mini-media-player
      entity: '[[entity_id]]'
      group: false
      tts:
        platform: alexa
      hide:
        power: true
        progress: true
      shortcuts:
        columns: 4
        buttons:
          - name: Gimmel
            type: script
            id: script.media_player_play_tunein_radio
            data:
              entity_id: '[[entity_id]]'
              content_id: Kan Gimmel
          - name: Bet
            type: script
            id: script.media_player_play_tunein_radio
            data:
              entity_id: m'[[entity_id]]'
              content_id: Kan Bet
          - name: Galatz
            type: script
            id: script.media_player_play_tunein_radio
            data:
              entity_id: '[[entity_id]]'
              content_id: Galei Zahal
          - name: 90 FM
            type: script
            id: script.media_player_play_tunein_radio
            data:
              entity_id: '[[entity_id]]'
              content_id: Radio 90 FM
          - name: 99 FM
            type: script
            id: script.media_player_play_tunein_radio
            data:
              entity_id: '[[entity_id]]'
              content_id: Echo 99 FM
          - name: Kan 88
            type: script
            id: script.media_player_play_tunein_radio
            data:
              entity_id: '[[entity_id]]'
              content_id: KAN 88
          - name: Galgalatz
            type: script
            id: script.media_player_play_tunein_radio
            data:
              entity_id: '[[entity_id]]'
              content_id: GLGLZ
          - id: script.media_player_play_tunein_radio
            type: source
```

## Lovelace

Set your media player entity id

```yaml
.
.
.
  type: vertical-stack
  cards:
    - type: custom:decluttering-card
      template: template_media_player_echo
      variables:
        - entity_id: media_player.< media player id>
```

![Radio Player](image.jpg)

---

I put a lot of work into making this repo and component available and updated to inspire and help others! I will be glad to receive thanks from you — it will give me new strength and add enthusiasm:
<p align="center"><br>
<a href="https://paypal.me/eyalco1967?locale.x=he_IL" target="_blank"><img src="http://khrolenok.ru/support_paypal.png" alt="PayPal" width="250" height="48"></a>
</p>