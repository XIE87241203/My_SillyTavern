【变量更新】
在所有文本的最后,进行变量更新。
以下是故事中需要追踪的关键变量,当前状态以这些变量的值为准。
<status_current_variables>
{{get_message_variable::stat_data}}
</status_current_variables>
严格按照以下规则和格式进行输出,并确定每一个变量是否需要更新,不要遗漏：
rule:
  description:
    - You should output the update analysis in the end of the next response, following the variables list defined in <status_current_variables> section which will be provided by the previous turn.
    - In context, variable updates are omitted by the system so they are not shown to you, but you should still add it.
    - There are 4 commands can be used to adjust the data: `_.set`, `_.assign`, `_.remove` and `_.add`.
    - to set a certain value, use `_.set`, it supports 2 or 3 input args.
    - to insert something into an array or object, use `_.assign`, it supports 2 or 3 input args.
    - to delete something from an object/array, use `_.remove`, it supports 1 or 2 input args.
    - If you need to assign or remove multiple values, use `_.assign` or `_.remove` multiple times, not in a single command.
    - to add a delta to a number, use `_.add`, it only supports 2 input args, and only supports modifications to numbers.
    - It is allowed to use math expressions for number inputs.
  analysis:
    - You must rethink what variables are defined in the previous <status_current_variables> property, and analyze how to update each of them accordingly.
    - For counting variables, change it when the corresponding event occur but don't change it any more during the same event.
    - When a numerical variable changes, check if it crosses any stage threshold and update to the corresponding stage.
    - If dest element is in an array with description, **PRECISELY** locate the element by adding "[0]" suffix. DO NOT change the description.
  format: |-
    <UpdateVariable>
        <Analysis>$(IN ENGLISH$)
            - calculate time passed: ...
            - decide whether dramatic updates are allowed as it's in a special case or the time passed is more than usual: yes or no
            - list every variable in `<status_current_variables>` section...
            - Check the description of this variable and analyze whether it satisfies its change conditions, do not output reason:...
            - Ignore summary related content when evaluate.
            ...
        </Analysis>
        _.set('${path}', ${old}?, ${new});//${reason}
        _.assign('${path}', ${key_or_index}?, ${value});//${reason}
        _.remove('${path}', ${key_or_index_or_value}?);//${reason}
        _.add('${path}', ${delta});//${reason}
    </UpdateVariable>
  example: |-
    <UpdateVariable>
        <Analysis>
            当前时间[0]: Y
            悠纪.好感度[0]: Y
            悠纪.重要成就[0]: Y
            悠纪.着装[0]: Y
            ...
        </Analysis>
        _.set('当前时间[0]', '2026-6-1 10:05', '2026-6-1 10:15');//时间流逝
        _.add('悠纪.好感度[0]', 2);//与悠纪的好感度增加
        _.assign('悠纪.重要成就[0]', '2026年6月1日,悠纪对<user>告白成功');//悠纪对<user>成功告白
        _.remove('悠纪.着装[0]', '粉色缎带');//悠纪脱下粉色缎带
    </UpdateVariable>