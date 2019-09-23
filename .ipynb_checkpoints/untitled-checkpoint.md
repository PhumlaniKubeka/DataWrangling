Shape (1555, 70)
Columns 
Index(['ID', 'Section 5 of 6 [I am always prepared.]',
       'Section 5 of 6 [I am easily disturbed.]',
       'Section 5 of 6 [I am exacting (demanding) in my work.]',
       'Section 5 of 6 [I am full of ideas.]',
       'Section 5 of 6 [I am interested in people.]',
       'Section 5 of 6 [I am not interested in abstract ideas.]',
       'Section 5 of 6 [I am not interested in other people's problems.]',
       'Section 5 of 6 [I am not really interested in others.]',
       'Section 5 of 6 [I am quick to understand things.]',
       'Section 5 of 6 [I am quiet around strangers.]',
       'Section 5 of 6 [I am relaxed most of the time.]',
       'Section 5 of 6 [I am the life of the party.]',
       'Section 5 of 6 [I change my mood a lot.]',
       'Section 5 of 6 [I do not have a good imagination.]',
       'Section 5 of 6 [I don't like to draw attention to myself.]',
       'Section 5 of 6 [I don't mind being the center of attention.]',
       'Section 5 of 6 [I don't talk a lot.]',
       'Section 5 of 6 [I feel comfortable around people.]',
       'Section 5 of 6 [I feel little concern for others.]',
       'Section 5 of 6 [I feel others' emotions.]',
       'Section 5 of 6 [I follow a schedule.]',
       'Section 5 of 6 [I get chores done right away.]',
       'Section 5 of 6 [I get irritated easily.]',
       'Section 5 of 6 [I get stressed out easily.]',
       'Section 5 of 6 [I get upset easily.]',
       'Section 5 of 6 [I have a rich vocabulary.]',
       'Section 5 of 6 [I have a soft (kind) heart.]',
       'Section 5 of 6 [I have a vivid imagination.]',
       'Section 5 of 6 [I have difficulty understanding abstract ideas.]',
       'Section 5 of 6 [I have excellent ideas.]',
       'Section 5 of 6 [I have frequent mood swings.]',
       'Section 5 of 6 [I have little to say.]',
       'Section 5 of 6 [I insult people.]',
       'Section 5 of 6 [I keep in the background.]',
       'Section 5 of 6 [I leave my belongings lying around.]',
       'Section 5 of 6 [I like order.]',
       'Section 5 of 6 [I make a mess of things.]',
       'Section 5 of 6 [I make people feel at ease.]',
       'Section 5 of 6 [I neglect my duties.]',
       'Section 5 of 6 [I often feel blue (down).]',
       'Section 5 of 6 [I often forget to put things back in their proper place]',
       'Section 5 of 6 [I pay attention to details.]',
       'Section 5 of 6 [I seldom feel blue (down).]',
       'Section 5 of 6 [I spend time reflecting on things.]',
       'Section 5 of 6 [I start conversations.]',
       'Section 5 of 6 [I sympathize with others' feelings.]',
       'Section 5 of 6 [I take time out for others.]',
       'Section 5 of 6 [I talk to a lot of different people at parties.]',
       'Section 5 of 6 [I use difficult words.]',
       'Section 5 of 6 [I worry about things.]', 'Unnamed: 51', 'Unnamed: 52',
       'Unnamed: 53', 'Unnamed: 54', 'Unnamed: 55', 'Unnamed: 56',
       'Unnamed: 57', 'Unnamed: 58', 'Unnamed: 59', 'Unnamed: 60',
       'Unnamed: 61', 'Unnamed: 62', 'Unnamed: 63', 'Unnamed: 64',
       'Unnamed: 65', 'Unnamed: 66', 'Unnamed: 67', 'Unnamed: 68',
       'IPIP_HIGH_RISK'],
      dtype='object')
      
 for (columnName, columnData) in personality_tidy.itertuples():
        count += columnData
    return count
    
  def hist_plots(x,y,data):
    for i in x:
        for j in y:
            xy = data[data['Department'] == f'{j}']
            sns.distplot(xy[j],bins = 10, kde=False)
            plt.xlabel(x)
            plt.ylabel(y)
            plt.show()
columns = ["Extraversion","Agreeableness","Conscientiousness","Neuroticism","Imagination"]
Department_g = ['Data','Web Dev','Copywriting','Design','Strategy']
merged_data.apply(hist_plots(columns,Department_g,merged_data), axis = 1)

neur_risk = merged_tidy[merged_data['Neuroticism_subscale'] == 'low']
Agree_risk = merged_tidy[merged_data['Agreeableness_subscale'] == 'low']
Cons_risk = merged_tidy[merged_data['Conscientiousnessn_subscale'] == 'low']