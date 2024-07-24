token = "MTA2NDA1NzA4ODcxMzY5MTE3Nw.GrgF7J.eU_Ai8kD7nUZ566nJmnUQI_0dTy7bGBXXaqOcE";// 

process.env.NODE_TLS_REJECT_UNAUTHORIZED = 1;

noti_key = "GLOMMII COMUNITY"
console.log("Glommii \nJoinDiscord: https://discord.gg/9V8pJjn3MG");
name_server = "**__GLOMMII COMUNITY__**"; 
invite_discord = "https://discord.gg/9V8pJjn3MG"; 
noti_config = {
  random_anime_picture: false,
  boss: true,
  sword: true,
  mirage: true,
  kitsune: true,
  haki: {
    normal: true,
    legend: true,
  },
  fullmoon: true,
  fruit_drop: true,
  king_legacy: true,
  near: true,
}; 

webhook_config = {
  boss: "https://discord.com/api/webhooks/1265242821275684894/09GJDgLqhwJNxA2Bqdcd8yG_cvEX92v0p1gq9YyTZkjdc_R85mYZOhCI7FgniGCVvlq4",
  sword: "https://discord.com/api/webhooks/1265242893296074803/b_dvPiuswM7EWUEMqcVDjcpAAreMoaJFvD_yJ0MnCg4PIIv3YIxewdj7hD11dkt49kGD",
  mirage: "https://discord.com/api/webhooks/1265233529844007016/Nc8kbhk6Mf3NbVCezejG8D4WgdFsoDn0IZCPu8uFKagfNqmmU6qzvXvd9PtKC_EUfwTP",
  kitsune: "https://discord.com/api/webhooks/1265243020123574394/poyavjRBwD03hb-D36ixxMR9X7_Vd67bdrnV4QZuPijKnICBDJh2bnAZd8GWPA-KEPxK",
  haki: {
    normal: "https://discord.com/api/webhooks/1265233162213130240/-XwB7US8V6VMbUThR29M_psDyx0AqYhKxBA9PYAtLVfph4MoQ35pkg0g5AmnmRR-7Lzf",
    legend: "https://discord.com/api/webhooks/1265466561561624626/W6s53Y0zcCLPuy8PxYWfKZCyFjFNY19mJra2Dov0LWXTwaVVKQthP4d5GN-aC5PPiu79",
  },
  fullmoon: "https://discord.com/api/webhooks/1265232420412592231/ZthrjvVYoatEfeI64OIYQs0n9CNOcbmUGGDmB20aTwsCpHB8OmWG2izFESD67MCFZ5jo",
  fruit_drop: "https://discord.com/api/webhooks/1265233308284092529/OQUe3yM6P6MLQhFgb5gQ7O7C3seItQ9W3QXUvfII18YrdSc1e2GUIn8Og5gwwugLGveL",
  king_legacy: "https://discord.com/api/webhooks/1265243935924813826/x4il8XQg0d-6ukBXbHh2R_Zy_mmucX5goQKZN3Owt7SHnscmBpTF05SZ-CYybcKGLwDF",
  near: "https://discord.com/api/webhooks/1265232632988303402/fIG-8XcP1lHNPK0uNxyJ8KkUsYF4nALOw5W4AqriLWjY1LnKh_856BdvUe569JbeEWV8",
  low: "https://discord.com/api/webhooks/1265291381815902208/YET3b9oHLc9ozDo6sPMoHJW2-SLxXemukhzr4xSOJ5xVITYzV5mTOxwnKjVJvUtX3I9K",
};

try {
    require.resolve("discord.js-selfbot-v13");
  } catch (e) {
    console.log("Please run: `npm install discord.js-selfbot-v13");
    process.exit(0);
  }
  
  try {
    require.resolve("discord.js");
  } catch (e) {
    console.log("Please run: `npm install discord.js");
    process.exit(0);
  }
  
  try {
    require.resolve("axios");
  } catch (e) {
    console.log("Please run: `npm install axios");
    process.exit(0);
  }
  
  const { Client, Intents } = require("discord.js-selfbot-v13");
  const { WebhookClient, EmbedBuilder } = require("discord.js");
  const client = new Client({
    intents: new Intents(7796),
    partials: [
      "USER",
      "CHANNEL",
      "GUILD_MEMBER",
      "MESSAGE",
      "REACTION",
      "GUILD_SCHEDULED_EVENT",
    ],
    checkUpdate: true,
  });
  
  const anime = async function (e) {
    e = e.toJSON();
    if (!noti_config.random_anime_picture) {
      return e;
    }
     const { data: sex_grayx_hub } = await require("axios").get(
      "",
    );
    e.content = noti_config.content;
    e.image = { url: sex_grayx_hub.url };
    return e;
  };
  
// dont edit some here ... pls
const ownerID = "1064057088713691177"; // ignore = error
avtOwner = "https://cdn.discordapp.com/avatars/1064057088713691177/5c80143a9ba6d2df68df1f49e5c9991b.png?size=4096";
nameOwner = "glommii";
client.on("ready", async () => {
    console.log(`Code được tạo bởi: Tôi`);
  console.log(`Successfully: code đang bắt đầu chạy`);
  client.user.setStatus("invisible");
  nameOwner = client.users.cache.get(ownerID).tag;
});

client.on("messageCreate", async (message) => {
  const channel = message.channelId;
  if (channel == "1226356041248280596" && noti_config.boss) {
    // boss royx
    const data = message.embeds[0].fields;
    const webhook = new WebhookClient({ url: webhook_config.boss });
    webhook.send({
      embeds: [
        await anime(
          new EmbedBuilder()
            .setTitle(" __Boss Spawn__" + name_server,)
            .setURL(invite_discord)
            .addFields(
              { name: "**[👺] __Boss Tên:__**", value: data[0].value.replace("True Form", ""),},
              //{ name: "**[🌊] __Sea World:__**", value: data[1].value },
              { name: "**[👤] __Người trong server:__**", value: data[1].value },
              { name: "**[🔗] __Job id:__**", value: data[2].value },
              { name: "**[📜] __Script tham gia server:__**", value: data[3].value },
            )
            .setTimestamp(Date.now())
            .setColor("f2e716")
            .setFooter({
              text: `Owner : @${nameOwner}`,
              iconURL: avtOwner,
            }),
        ),
      ],
    });

} else if (channel == "1190876054026457148" && noti_config.sword) {
    // sword cac
    const data = message.embeds[0].fields;
    const webhook = new WebhookClient({ url: webhook_config.sword });
    webhook.send({
      embeds: [
           await anime(
          new EmbedBuilder()
            .setTitle(" __Sword Legend__" + name_server,)
            .setURL(invite_discord)
            .addFields(
              { name: "**[⚔️] __Sword Name:__**", value: data[0].value },
              { name: "**[🌊] __Sea:__**", value: data[1].value },
              { name: "**[👤] __Người trong server:__**", value: data[2].value },
              { name: "**[🔗] __Job id:__**", value: data[3].value },
              { name: "**[📜] __Script tham gia server:__**", value: data[4].value },
            )
            .setTimestamp(Date.now())
            .setColor("f2e716")
            .setFooter({
              text: `Created By: @${nameOwner}`,
              iconURL: avtOwner,
            }),
        ),
      ],
    });
  } else if (channel == "1190876089061478431" && noti_config.mirage) {
    // mirage maru
    const data = message.embeds[0].fields;
    const webhook = new WebhookClient({ url: webhook_config.mirage });
    webhook.send({
      embeds: [
        await anime(
          new EmbedBuilder()
            .setTitle(" Mirage Island" + name_server,)
            .setURL(invite_discord)
            .addFields(
              { name: "**[🏝️] __Đảo bí ẩn ra lò:__**", value: `\`\`\`✅\`\`\`` },
              { name: "**[🌊] __sea:__**", value: `\`\`\`3\`\`\`` }, 
                //{ name: "**[🌊] __Sea:__**", value: data[0].value },
              { name: "**[⏳] __Thời gian ra trong server:__**", value: data[0].value },
              { name: "**[👤] __Người chơi trong server:__**", value: data[1].value },
              { name: "**[🔗] __Job id:__**", value: data[2].value },
              { name: "**[📜] __Script tham gia server:__**", value: data[3].value },
            )
            .setTimestamp(Date.now())
            .setColor("f2e716")
            .setFooter({
              text: `Owner : @${nameOwner}` ,
              iconURL: avtOwner,
            }),
        ),
      ],
    });
  
  } else if (channel == "1190874818510323722" && noti_config.haki.legend) {
    // haki legendary maru
    const data = message.embeds[0].fields;
    const webhook = new WebhookClient({ url: webhook_config.haki.legend });
    webhook.send({
      embeds: [
        await anime(
          new EmbedBuilder()
            .setTitle(" __Haki Legendary__" + name_server,)
            .setURL(invite_discord)
            .addFields(
              { name: "**[🌈]__Haki hiếm tên:__**", value: data[0].value },
              //{ name: "**[🌊] __Sea World:__**", value: data[1].value },
              { name: "**[👤]__Người trong server:__**", value: data[1].value },
              { name: "**[🔗]__Job id:__**", value: data[2].value },
              { name: "**[📜]__Script tham gia server:__**", value: data[3].value },
            )
            .setTimestamp(Date.now())
            .setColor("f2e716")
            .setFooter({
              text: `Owner : @${nameOwner}` ,
              iconURL: avtOwner,
            }),
        ),
      ],
    });
  
  } else if (channel == "1190483035817255003" && noti_config.haki.normal) {
    // haki normal xero
    const data = message.embeds[0].fields;
    const webhook = new WebhookClient({ url: webhook_config.haki.normal });
    webhook.send({
      embeds: [
        await anime(
          new EmbedBuilder()
            .setTitle(
                " __Haki Normal__" + name_server,)
            .setURL(invite_discord)
            .addFields(
              { name: "**[🎨] __Haki bình thường:__**", value: data[0].value },
              //{ name: "**[🌊] __Sea World:__**", value: data[1].value },
              { name: "**[👤] __Người trong server:__**", value: data[1].value },
              { name: "**[🔗] __Job id:__**", value: data[2].value },
              { name: "**[📜] __Script tham gia server:__**", value: data[3].value },
            )
            .setTimestamp(Date.now())
            .setColor("f2e716")
            .setFooter({
              text: `Owner : @${nameOwner}` ,
              iconURL: avtOwner,
            }),
        ),
      ],
    });

  } else if (channel == "1200833992933519400" && noti_config.fullmoon) {
    // full moon azuzu
    const data = message.embeds[0].fields;
    const webhook = new WebhookClient({ url: webhook_config.fullmoon });
    webhook.send({
      embeds: [
        await anime(
          new EmbedBuilder()
            .setTitle(
              " Full Moon" + name_server,)
            .setURL(invite_discord)
            .addFields(
                { name: "**[🌑] __Full Moon:__**", value: `\`\`\`✅\`\`\`` },
                { name: "**[⏳] __Thời gian còn lại:__**", value: data[0].value },
                { name: "**[👤] __Trăng:__**", value: data[1].value },
                { name: "**[👤] __Người trong server:__**", value: data[2].value },
                { name: "**[🔗] __Job id:__**", value: data[3].value },
                { name: "**[📜] __Script tham gia server:__**", value: data[4].value },
            )
            .setTimestamp(Date.now())
            .setColor("f2e716")
            .setFooter({
              text: `Owner : @${nameOwner}` ,
              iconURL: avtOwner,
            }),
        ),
      ],
    });
  
} else if (channel == "1190581854185721866" && noti_config.fruit_drop) {
  // fruit drop banana
  const data = message.embeds[0].fields;
  const webhook = new WebhookClient({ url: webhook_config.fruit_drop });
  webhook.send({
    embeds: [
      await anime(
        new EmbedBuilder()
          .setTitle( " __Fruit Drop__" + name_server, )
          .setURL(invite_discord)
          .addFields(
            { name: "**[🥝] - __Fruit tên :__**", value: data[0].value },
            //{ name: "**[🎋] - __Location ( Sea ) :__**", value: data[1].value },
            { name: "**[👥] - __Người trong server:__**", value: data[1].value },
            { name: "**[🔗] - __Job id:__**", value: data[2].value },
            { name: "**[📋] - __Script tham gia server:__**", value: data[3].value }, 
            )
          .setTimestamp(Date.now())
          .setColor("f2e716")
          .setFooter({ text: `Created By: @${nameOwner}` , iconURL: avtOwner, }),
      ),
    ],
  });

} else if (channel == "1225459275103600671" && noti_config.king_legacy) {
  // king legacy maru
  const data = message.embeds[0].fields;
  const webhook = new WebhookClient({ url: webhook_config.king_legacy });
  webhook.send({
    embeds: [
      await anime(
        new EmbedBuilder()
          .setTitle("__ᴋɪɴɢ ʟᴇɢᴀᴄʏ__"+ name_server)
          .setURL(invite_discord)
          .addFields(
            { name: "**[🐯] - __Boss Name :__**", value: data[2].value.replace("```yaml\n", "```").replace("\n```", "```") },
            { name: "**[⏳] - __Thời gian máy chủ:__**", value: data[0].value.replace("```yaml\n", "```").replace("\n```", "```") },
            { name: "**[👥] - __Người trong server:__**", value: data[1].value.replace("```yaml\n", "```").replace("\n```", "```") },
            { name: "**[🔗] - __Job id:__**", value: data[3].value.replace("```yaml\n", "```").replace("\n```", "```") },
            { name: "**[📋] - __Script tham gia server:__**", value: data[4].value }, )
          .setTimestamp(Date.now())
          .setColor("f2e716")
          .setFooter({ text: `Owner : @${nameOwner}`, iconURL: avtOwner, }),
      ),
    ],
  });

}else if (channel == "1208655936344825887" && noti_config.kitsune) {
  // kitsune Xero
  const data = message.embeds[0].fields;
  const webhook = new WebhookClient({ url: webhook_config.kitsune });
  webhook.send({
    embeds: [
      await anime(
        new EmbedBuilder()
          .setTitle(" __Kitsune Spawn__ " + name_server, )
          .setURL(invite_discord)
          .addFields(
            { name: "**[🦊] __Đảo kitsune:__**", value: `\`\`\`✅\`\`\`` },
            { name: "**[🌊] __sea:__**", value: `\`\`\`3\`\`\`` },  
            //{ name: "**[🦊] __Kitsune Island:__**", value: data[0].value },
            //{ name: "**[🌊] __Sea World:__**", value: data[].value },
            //{ name: "**[🌊] __Sea:__**", value: data[0].value },  
            { name: "**[👥] - __Người trong server:__**", value: data[0].value },
            { name: "**[🔗] - __Job id:__**", value: data[1].value },
            { name: "**[📋] - __Script tham gia server:__**", value: data[2].value },
            )
          .setTimestamp(Date.now())
          .setColor("f2e716")
          .setFooter({ text: `Owner : @${nameOwner}`, iconURL: avtOwner, }),
      ),
    ],
  });


} else if (channel == "1208655409712340994" && noti_config.near) {
  // near moon w-azre
  const data = message.embeds[0].fields;
  const webhook = new WebhookClient({ url: webhook_config.near });
  webhook.send({
    embeds: [
      await anime(
        new EmbedBuilder()
          .setTitle(" __Near Full Moon__" + name_server,)
          .setURL(invite_discord)
          .addFields(
            { name: "**[👤] __Player Count:__**", value: data[0].value },
            { name: "**[👤] __[⏳] Time :__**", value: data[1].value },
            { name: "**[<:timers:1199736361972932679>]__Current Time:__**", value: data[2].value },
            { name: "**[🔗] __Job ID:__**", value: data[3].value },
            { 
              name: "**[📜] __Script Join:__**", 
              value: (data[4] && data[4].value) ? data[4].value : 'No data available' 
          }
          )
          .setTimestamp(Date.now())
          .setColor("f2e716")
          .setFooter({
            text: `Owner : @${nameOwner}`,
            iconURL: avtOwner,
          }),
      ),
    ],
  });
}
});



client.login(token);
