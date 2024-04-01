<h1  align="center">
  Olá, como vai?
</h1>

Atualmente moro em São Paulo, tenho 20 anos e estou cursando o quarto semestre de engenharia de software. Minhas principais ferramentas são Typescript, Node/Express e React, mas também utilizo Rust e possuo alguns projetos com Java.

Meu primeiro contato com a programação foi em um curso de gamedev que vim a concluir em 2018, mas só comecei a criar meus projetos quando decidi seguir a grade currícular do [The Odin Project](https://www.theodinproject.com/paths/full-stack-javascript), no início da minha faculdade.

[Página do LinkedIn](https://www.linkedin.com/in/silva-luc/) e [Portfólio](https://luc-silva.github.io/portfolio/) 


[![wakatime](https://wakatime.com/badge/user/c1b7afcb-168f-4074-bcff-1c6756fac9a3.svg)](https://wakatime.com/@c1b7afcb-168f-4074-bcff-1c6756fac9a3)
![](https://komarev.com/ghpvc/?username=luc-silva&color=blue)

> Projetos Recentes
- [Electroware](https://github.com/luc-silva/electroware)
- [Bookwise](https://github.com/luc-silva/Bookwise)
- [Taskbuddy](https://github.com/luc-silva/Taskbuddy)
- [Portfolio](https://github.com/luc-silva/portfolio)
<!--  
[![tryhackme]( https://tryhackme-badges.s3.amazonaws.com/luc.silva.png)](https://tryhackme.com/p/luc.silva)



![]( https://github-readme-stats.vercel.app/api?username=luc-silva&count_private=true&theme=github_dark&show_icons=true&card_width=500px)
![](https://leetcode.card.workers.dev/luc-silva?theme=auto&font=baloo&extension=null)
https://www.youtube.com/watch?v=NmU2nNehNNY
[![GitHub Streak](https://streak-stats.demolab.com?user=luc-silva&theme=radical&hide_border=true&date_format=M%20j%5B%2C%20Y%5D&mode=weekly)](https://git.io/streak-stats) ![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=luc-silva&layout=compact&theme=radical)

export default validateRequest({ methods: ['PUT'] }, async (req, res) => {
  const session = await ensureGetSession({ req });
  const errors: ErrorData[] = [];

  await req.body.forEach(async (item: Zod.infer<typeof editQidVmItemZod>) => {
    try {
      const qidVmExist = (await checkIfQidvmExist(item)) as IQidVm[];

      if (qidVmExist.length > 0) {
        const data = editQidVmItemZod.parse(item);
        await editQidVm(data, Number(session.user.idMat));
      } else {
        const data = createQidVmZod.parse(item);
        await createQidVm(data, Number(session.user.idMat));
      }
    } catch (e: any) {
      errors.push({
        ...item,
        errorDetails: {
          message: e.message,
        },
      });
      //console.log(errors);
    }
  });

  console.log(errors);
  if (errors.length > 0) {
    return res.status(207).send({ ok: 'erro', errors });
  }
  return res.status(200).send({ ok: 'success' });
});
